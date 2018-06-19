---
title: 如何部署自定义适配器 |Microsoft 文档
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
ms.openlocfilehash: e36443b99f01688a38e66a4a302ab64bb220092f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22250293"
---
# <a name="how-to-deploy-a-custom-adapter"></a>如何部署自定义适配器
一个完整的适配器安装过程包括以下步骤：  
  
1.  检查依存关系。 例如，MSMQ 适配器安装程序检查本地是否存在 MSMQ 服务，因为该适配器运行时依赖此服务。  
  
2.  设置本地文件系统。 这包括创建安装文件夹以及复制二进制文件和支持文件。 确保文件夹和文件访问权限配置正确。  
  
3.  将托管程序集安装在系统全局程序集缓存中。  
  
4.  创建适配器的注册表项。  
  
    > [!NOTE]
    >  对于 32 位适配器，BizTalk Server 管理控制台使用注册表中的 HKEY_CLASSES_ROOT 分支获取自定义适配器配置。  如果在 64 位服务器上安装 32 位适配器，则 BizTalk Serve 管理控制台使用 HKEY_CLASSES_ROOT\Wow6432Node\ 分支获取适配器配置数据。  
  
5.  将适配器添加到 BizTalk Server。 这意味着在 BizTalk 管理数据库中为适配器以及为用于反映适配器所升级的属性的属性架构添加新条目。 有时会使用 BizTalk Server 管理控制台手动完成此步骤。  
  
## <a name="exceptions"></a>异常  
 在进行 BizTalk Server 的非完整安装时，适配器安装程序可能不需要检查依存关系。 例如，在仅安装管理工具时，适配器安装程序不需要检查适配器运行时依存关系，因为不使用适配器运行时。 同样，在仅安装 BizTalk Server 运行时的时候，适配器安装程序也不需要检查适配器设计时依存关系。  
  
 在多 BizTalk Server 环境中，前面所列步骤中的最后一步（将适配器添加到 BizTalk Server）仅当在第一个 BizTalk Server 上安装适配器时才需要。 这是因为所有 BizTalk Server 服务实例都共享同一个 BizTalk 管理数据库（默认名称为 BizTalkMgmtDB）。 如果将适配器添加到同组的其他 BizTalk 服务器中，则这些附加的安装步骤会失败。  
  
## <a name="install-the-adapter-assemblies-into-the-global-assembly-cache"></a>将适配器程序集安装在全局程序集缓存中  
 为了支持具有不同适配器安装路径的多 BizTalk Server 主机环境，必须将适配器程序集安装在系统全局程序集缓存中。  
  
 在适配器安装和配置过程中，会在 BizTalk 管理数据库（默认名称为 BizTalkMgmtDB）的 adm_adapter 表中创建一个新适配器条目。 此条目包含 BizTalk Server 运行时和设计时使用的所有引用信息。  
  
 **InBoundAssemblyPath**和**OutboundAssemblyPath**字段由 BizTalk Server 运行时，若要了解加载适配器二进制文件的位置。 因为一个 BizTalk Server 组只有一个 BizTalk 管理数据库，所以组中的所有 BizTalk 服务器必须共享这同一条信息。 如果要将适配器安装在组内的不同 BizTalk 服务器上，则必须在每台这样的服务器上都使用同一条安装路径。 如果本地安装路径与 BizTalk 管理数据库存储的路径不同，则 BizTalk Server 无法加载适配器二进制文件。  
  
 在适配器安装过程中，应始终用强名称签署适配器的程序集，并使用 Gacutil.exe 将适配器程序集放在系统全局程序集缓存中。 请确保你保留**InBoundAssemblyPath**和**OutboundAssemblyPath**字段为 null，或为空。  
  
## <a name="using-the-framework-for-adapter-configuration"></a>使用适配器框架配置  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]为适配器配置用户界面 (UI) 提供对生成的属性表的机制。 它基于配置属性的 XML 架构定义 (XSD) 所做的定义。 使用此框架给适配器开发人员带来很大的挑战。 本部分为应对其中的部分问题提供了有效的对策。  
  
### <a name="consider-custom-property-editors-for-all-your-key-properties"></a>对所有关键属性考虑使用自定义属性编辑器  
 把重要的属性验证放在属性页的顶部属性中，是不可能的。 框架尝试使用 XML 架构定义 (XSD) 的 simpleType 限制来定义 UI 的验证规则。 采用了简单的最大和最小值规则，但不支持字符串字段的正则表达式限制。 另外，在应用限制之前，数据被转换为公共语言运行时 (CLR) 类型。 这意味着 UI 用户有时会收到加密的类型转换错误，而不会收到越界错误。 总而言之，验证逻辑很弱。  
  
 很多适配器开发人员都采纳的解决方案是，为属性页的主要属性编写自定义属性编辑器。 如果有很多相互依存的属性（通常会是这种情况），则自定义属性编辑器可以将结果合并到单个字段中，以后运行时可以将这些结果分开。 这是将必要的（尽管一般来说是微不足道的）自定义代码放入接口的唯一办法。  
  
 自定义属性编辑器的编写相对简单，对 XSD 中的属性做批注就可以使用自定义属性编辑器。 批注引用提供属性编辑器入口点的程序集，并通过编码显示为 CLR 窗体。 现在，您可以编写常规用户界面和使用 Visual Studio 提供的传统界面生成工具。  
  
 以下代码显示如何使用 XSD 添加一个自定义属性编辑器：  
  
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
  
 引用的代码应像下面这样：  
  
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
  
 由于必须让管理运行时能找到 XSD 中引用的程序集，因此应该将此程序集添加到全局程序集缓存中。