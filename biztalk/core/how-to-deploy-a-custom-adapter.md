---
title: 如何部署自定义适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f17b336c-6232-4889-ab7e-92b83fab0f5f
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2d04638aef5172eba3bae57a6f0d315fad66162
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385298"
---
# <a name="how-to-deploy-a-custom-adapter"></a>如何部署自定义适配器
完整的适配器安装过程包括以下步骤：  
  
1.  检查依赖关系。 例如，MSMQ 适配器安装程序的本地 MSMQ 服务存在检查，因为适配器运行时依赖于它。  
  
2.  设置本地文件系统。 这包括创建安装文件夹以及复制二进制文件和支持文件。 请确保对文件夹的访问和文件访问权限配置正确。  
  
3.  将托管程序集安装到系统全局程序集缓存。  
  
4.  创建适配器的注册表项。  
  
    > [!NOTE]
    >  对于 32 位适配器，BizTalk Server 管理控制台使用注册表中的 HKEY_CLASSES_ROOT 分支获取自定义适配器配置。  如果在 64 位服务器上安装 32 位适配器，BizTalk Serve 管理控制台改为使用 hkey_classes_root\wow6432node \ 分支获取适配器配置数据。  
  
5.  将适配器添加到 BizTalk Server。 这意味着适配器也用于反映适配器所升级的属性的属性架构的 BizTalk 管理数据库中的新条目。 有时使用 BizTalk Server 管理控制台手动完成此步骤。  
  
## <a name="exceptions"></a>Exceptions  
 适配器安装程序可能不需要检查部分的 BizTalk Server 安装中的依赖项。 例如，在管理仅工具安装中，适配器安装程序不会不需要检查适配器运行时依赖项，因为不使用适配器运行时。 这同样适用在 BizTalk Server 仅限运行时的安装中，其中适配器安装程序不需要检查适配器设计时依赖关系。  
  
 在多个 BizTalk Server 环境中，前面的列表 （添加到 BizTalk Server 适配器） 的最后一步仅发生在第一个 BizTalk Server 上安装适配器。 这是因为所有 BizTalk Server 服务实例都共享相同的 BizTalk 管理数据库 （具有默认名称为 BizTalkMgmtDB）。 如果将适配器添加到同一个组中的其他 BizTalk 服务器，其他步骤失败。  
  
## <a name="install-the-adapter-assemblies-into-the-global-assembly-cache"></a>将适配器程序集安装到全局程序集缓存  
 若要支持多个 BizTalk Server 主机环境使用不同适配器安装路径，必须在系统全局程序集缓存安装适配器程序集。  
  
 在适配器安装和配置，在 BizTalk 管理数据库 （具有默认名称为 BizTalkMgmtDB） 的 adm_adapter 表中创建一个新适配器条目。 此条目包含 BizTalk Server 运行的时和设计时使用的所有参考信息。  
  
 **InBoundAssemblyPath**并**OutboundAssemblyPath**字段由 BizTalk Server 运行时，用于找出加载适配器二进制文件的位置。 由于没有为 BizTalk Server 组只有一个 BizTalk 管理数据库，在组中的所有 BizTalk server 必须都共享这同一条信息。 如果你想要在组内的不同 BizTalk 服务器上安装适配器，您必须在每台服务器上使用的相同安装路径。 如果本地安装路径是从 BizTalk 管理数据库中存储的路径不同，BizTalk Server 无法加载适配器二进制文件。  
  
 始终使用强名称的适配器的程序集签名并使用 Gacutil.exe 将适配器安装过程将适配器程序集放入系统全局程序集缓存。 请确保您离开**InBoundAssemblyPath**并**OutboundAssemblyPath**字段为 null，或为空。  
  
## <a name="using-the-framework-for-adapter-configuration"></a>适配器配置为使用框架  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 为适配器配置用户界面 (UI) 提供用于生成属性页的机制。 它基于配置属性的 XML 架构定义 (XSD) 定义。 使用此框架为适配器开发人员引入了重大挑战。 本节提供了有效的解决方法建议为其中一些问题。  
  
### <a name="consider-custom-property-editors-for-all-your-key-properties"></a>为所有关键属性考虑自定义属性编辑器  
 就无法将基于属性的重要的属性验证放在属性表中。 框架尝试使用 XML 架构定义 (XSD) 的 simpleType 限制来定义 UI 的验证规则。 最大和最小值的简单规则会应用，但不是支持字符串字段的正则表达式限制。 此外，数据被转换为公共语言运行时 (CLR) 类型之前应用了限制。 这意味着 UI 用户有时获取含义模糊的类型转换错误而不是超出范围错误。 总而言之，验证逻辑是非常不可靠。  
  
 很多适配器开发人员都采纳的解决方案是在属性页上编写自定义属性编辑器中提供的主要属性。 如果有大量相互依存的属性 （如通常都是如此），然后自定义属性编辑器可以将结果合并到单个字段，并在运行时更高版本可以，分隔它们。 这是在界面获取必要的 （尽管一般来说是微不足道的） 自定义代码的唯一方法。  
  
 自定义属性编辑器的编写相对简单，可以批注 XSD 中的属性来使用它们。 批注引用的程序集公开的属性编辑器入口点，并通过编码来显示 CLR 窗体。 你现在可以编写常规用户界面，并使用 Visual Studio 提供的传统界面生成工具。  
  
 下面的代码演示如何使用 XSD 添加一个自定义属性编辑器：  
  
```  
<xs:element name="queueDetails" type="xs:string" minOccurs="0">  
    <xs:annotation>  
        <xs:appinfo>  
           <baf:designer>  
               <baf:displayname _locID="queueName">Queue Definition</baf:displayname>  
               <baf:description _locID="receiveQueueDesc">Details of MQSeries Server, Queue Manager and Queue from where you want to receive messages.</baf:description>  
               <baf:category _locID="mqsCategory">MQSeries</baf:category>  
               <baf:editor assembly="Microsoft.BizTalk Server.Adapter.MQSAdmin.dll">Microsoft.BizTalk Server.Adapter.MQSAdmin.MQSUITypeEditor</baf:editor>  
            </baf:designer>  
        </xs:appinfo>  
    </xs:annotation>  
</xs:element>  
  
```  
  
 引用的代码应如下所示：  
  
```  
public class MQSUITypeEditor : System.Drawing.Design.UITypeEditor  
{  
public override System.Drawing.Design.UITypeEditorEditStyle GetEditStyle  
(System.ComponentModel.ITypeDescriptorContext context)   
{  
return System.Drawing.Design.UITypeEditorEditStyle.Modal;  
}  
public override object EditValue (System.ComponentModel.ITypeDescriptorContext context,  
System.IServiceProvider provider, object value)   
{  
Form qdForm = new QueueDefinitionForm(value);  
IWindowsFormsEditorService service =   
(IWindowsFormsEditorService)provider.GetService(typeof(IWindowsFormsEditorService));  
DialogResult dialogResult = service.ShowDialog(qdForm);  
//…  
}  
}  
class QueueDefinitionForm : System.Windows.Forms.Form   
{  
//  traditional UI code goes here!  
}  
  
```  
  
 管理运行时必须能够找到引用在 XSD 中，因此应将其添加到全局程序集缓存的程序集。