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
# <a name="how-to-deploy-a-custom-adapter"></a><span data-ttu-id="6bc24-102">如何部署自定义适配器</span><span class="sxs-lookup"><span data-stu-id="6bc24-102">How to Deploy a Custom Adapter</span></span>
<span data-ttu-id="6bc24-103">完整的适配器安装过程包括以下步骤：</span><span class="sxs-lookup"><span data-stu-id="6bc24-103">A complete adapter installation process consists of the following steps:</span></span>  
  
1.  <span data-ttu-id="6bc24-104">检查依赖关系。</span><span class="sxs-lookup"><span data-stu-id="6bc24-104">Check dependencies.</span></span> <span data-ttu-id="6bc24-105">例如，MSMQ 适配器安装程序的本地 MSMQ 服务存在检查，因为适配器运行时依赖于它。</span><span class="sxs-lookup"><span data-stu-id="6bc24-105">For example, the MSMQ adapter installer checks for the existence of the local MSMQ service because the adapter runtime depends on it.</span></span>  
  
2.  <span data-ttu-id="6bc24-106">设置本地文件系统。</span><span class="sxs-lookup"><span data-stu-id="6bc24-106">Set up the local file system.</span></span> <span data-ttu-id="6bc24-107">这包括创建安装文件夹以及复制二进制文件和支持文件。</span><span class="sxs-lookup"><span data-stu-id="6bc24-107">This includes creating installation folders and copying binary and support files.</span></span> <span data-ttu-id="6bc24-108">请确保对文件夹的访问和文件访问权限配置正确。</span><span class="sxs-lookup"><span data-stu-id="6bc24-108">Ensure access to folders and file access permissions are configured properly.</span></span>  
  
3.  <span data-ttu-id="6bc24-109">将托管程序集安装到系统全局程序集缓存。</span><span class="sxs-lookup"><span data-stu-id="6bc24-109">Install managed assemblies into the system global assembly cache.</span></span>  
  
4.  <span data-ttu-id="6bc24-110">创建适配器的注册表项。</span><span class="sxs-lookup"><span data-stu-id="6bc24-110">Create registry keys for the adapter.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6bc24-111">对于 32 位适配器，BizTalk Server 管理控制台使用注册表中的 HKEY_CLASSES_ROOT 分支获取自定义适配器配置。</span><span class="sxs-lookup"><span data-stu-id="6bc24-111">For a 32-bit adapter, the BizTalk Server Administration Console uses the HKEY_CLASSES_ROOT branch in the registry to obtain custom adapter configuration.</span></span>  <span data-ttu-id="6bc24-112">如果在 64 位服务器上安装 32 位适配器，BizTalk Serve 管理控制台改为使用 hkey_classes_root\wow6432node \ 分支获取适配器配置数据。</span><span class="sxs-lookup"><span data-stu-id="6bc24-112">If a 32-bit adapter is installed on a 64-bit server, the BizTalk Serve Administration Console instead uses the HKEY_CLASSES_ROOT\Wow6432Node\ branch for adapter configuration data.</span></span>  
  
5.  <span data-ttu-id="6bc24-113">将适配器添加到 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="6bc24-113">Add the adapter to BizTalk Server.</span></span> <span data-ttu-id="6bc24-114">这意味着适配器也用于反映适配器所升级的属性的属性架构的 BizTalk 管理数据库中的新条目。</span><span class="sxs-lookup"><span data-stu-id="6bc24-114">This means new entries in the BizTalk Management database for the adapter as well as for the property schema used to reflect properties the adapter promotes.</span></span> <span data-ttu-id="6bc24-115">有时使用 BizTalk Server 管理控制台手动完成此步骤。</span><span class="sxs-lookup"><span data-stu-id="6bc24-115">This step is sometimes done manually using the BizTalk Server Administration console.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="6bc24-116">Exceptions</span><span class="sxs-lookup"><span data-stu-id="6bc24-116">Exceptions</span></span>  
 <span data-ttu-id="6bc24-117">适配器安装程序可能不需要检查部分的 BizTalk Server 安装中的依赖项。</span><span class="sxs-lookup"><span data-stu-id="6bc24-117">The adapter installer may not need to check the dependencies in partial BizTalk Server installations.</span></span> <span data-ttu-id="6bc24-118">例如，在管理仅工具安装中，适配器安装程序不会不需要检查适配器运行时依赖项，因为不使用适配器运行时。</span><span class="sxs-lookup"><span data-stu-id="6bc24-118">For example, in an administration tools-only installation, the adapter installer does not need to check adapter runtime dependencies because the adapter runtime is not used.</span></span> <span data-ttu-id="6bc24-119">这同样适用在 BizTalk Server 仅限运行时的安装中，其中适配器安装程序不需要检查适配器设计时依赖关系。</span><span class="sxs-lookup"><span data-stu-id="6bc24-119">The same is true in the BizTalk Server runtime-only installation, where the adapter installer does not need to check the adapter design-time dependencies.</span></span>  
  
 <span data-ttu-id="6bc24-120">在多个 BizTalk Server 环境中，前面的列表 （添加到 BizTalk Server 适配器） 的最后一步仅发生在第一个 BizTalk Server 上安装适配器。</span><span class="sxs-lookup"><span data-stu-id="6bc24-120">In multiple BizTalk Server environments, the last step in the preceding list (Add the adapter to BizTalk Server) only happens in the adapter installation on the first BizTalk Server.</span></span> <span data-ttu-id="6bc24-121">这是因为所有 BizTalk Server 服务实例都共享相同的 BizTalk 管理数据库 （具有默认名称为 BizTalkMgmtDB）。</span><span class="sxs-lookup"><span data-stu-id="6bc24-121">This is because all BizTalk Server service instances share the same BizTalk Management database (with the default name, BizTalkMgmtDB).</span></span> <span data-ttu-id="6bc24-122">如果将适配器添加到同一个组中的其他 BizTalk 服务器，其他步骤失败。</span><span class="sxs-lookup"><span data-stu-id="6bc24-122">If adapters are added to other BizTalk servers in the same group, the additional steps fail.</span></span>  
  
## <a name="install-the-adapter-assemblies-into-the-global-assembly-cache"></a><span data-ttu-id="6bc24-123">将适配器程序集安装到全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="6bc24-123">Install the Adapter Assemblies into the Global Assembly Cache</span></span>  
 <span data-ttu-id="6bc24-124">若要支持多个 BizTalk Server 主机环境使用不同适配器安装路径，必须在系统全局程序集缓存安装适配器程序集。</span><span class="sxs-lookup"><span data-stu-id="6bc24-124">To support multiple BizTalk Server host environments with different adapter installation paths, the adapter assemblies must be installed into the system global assembly cache.</span></span>  
  
 <span data-ttu-id="6bc24-125">在适配器安装和配置，在 BizTalk 管理数据库 （具有默认名称为 BizTalkMgmtDB） 的 adm_adapter 表中创建一个新适配器条目。</span><span class="sxs-lookup"><span data-stu-id="6bc24-125">During the adapter installation and configuration, a new adapter entry is created in the adm_adapter table of the BizTalk Management database (with the default name BizTalkMgmtDB).</span></span> <span data-ttu-id="6bc24-126">此条目包含 BizTalk Server 运行的时和设计时使用的所有参考信息。</span><span class="sxs-lookup"><span data-stu-id="6bc24-126">This entry contains all reference information used by BizTalk Server for both run time and design time.</span></span>  
  
 <span data-ttu-id="6bc24-127">**InBoundAssemblyPath**并**OutboundAssemblyPath**字段由 BizTalk Server 运行时，用于找出加载适配器二进制文件的位置。</span><span class="sxs-lookup"><span data-stu-id="6bc24-127">The **InBoundAssemblyPath** and **OutboundAssemblyPath** fields are used by the BizTalk Server runtime to find out where to load the adapter binaries.</span></span> <span data-ttu-id="6bc24-128">由于没有为 BizTalk Server 组只有一个 BizTalk 管理数据库，在组中的所有 BizTalk server 必须都共享这同一条信息。</span><span class="sxs-lookup"><span data-stu-id="6bc24-128">Because there is only one BizTalk Management database for a BizTalk Server group, all BizTalk servers in the group must share this same piece of information.</span></span> <span data-ttu-id="6bc24-129">如果你想要在组内的不同 BizTalk 服务器上安装适配器，您必须在每台服务器上使用的相同安装路径。</span><span class="sxs-lookup"><span data-stu-id="6bc24-129">If you want to install the adapter on different BizTalk servers within the group, you must use the same installation path on each of those servers.</span></span> <span data-ttu-id="6bc24-130">如果本地安装路径是从 BizTalk 管理数据库中存储的路径不同，BizTalk Server 无法加载适配器二进制文件。</span><span class="sxs-lookup"><span data-stu-id="6bc24-130">If the local installation path is different from the path stored in the BizTalk Management database, BizTalk Server cannot load the adapter binaries.</span></span>  
  
 <span data-ttu-id="6bc24-131">始终使用强名称的适配器的程序集签名并使用 Gacutil.exe 将适配器安装过程将适配器程序集放入系统全局程序集缓存。</span><span class="sxs-lookup"><span data-stu-id="6bc24-131">Always sign the adapter's assembly with a strong name and use Gacutil.exe to put the adapter assembly into the system global assembly cache during the adapter installation.</span></span> <span data-ttu-id="6bc24-132">请确保您离开**InBoundAssemblyPath**并**OutboundAssemblyPath**字段为 null，或为空。</span><span class="sxs-lookup"><span data-stu-id="6bc24-132">Make sure that you leave the **InBoundAssemblyPath** and **OutboundAssemblyPath** fields null, or empty.</span></span>  
  
## <a name="using-the-framework-for-adapter-configuration"></a><span data-ttu-id="6bc24-133">适配器配置为使用框架</span><span class="sxs-lookup"><span data-stu-id="6bc24-133">Using the Framework for Adapter Configuration</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="6bc24-134">为适配器配置用户界面 (UI) 提供用于生成属性页的机制。</span><span class="sxs-lookup"><span data-stu-id="6bc24-134">provides a mechanism for generating property sheets for the adapter configuration user interface (UI).</span></span> <span data-ttu-id="6bc24-135">它基于配置属性的 XML 架构定义 (XSD) 定义。</span><span class="sxs-lookup"><span data-stu-id="6bc24-135">It is based on an XML Schema Definition (XSD) definition of the configuration properties.</span></span> <span data-ttu-id="6bc24-136">使用此框架为适配器开发人员引入了重大挑战。</span><span class="sxs-lookup"><span data-stu-id="6bc24-136">The use of this framework introduces significant challenges for the adapter developer.</span></span> <span data-ttu-id="6bc24-137">本节提供了有效的解决方法建议为其中一些问题。</span><span class="sxs-lookup"><span data-stu-id="6bc24-137">This section suggests an effective workaround for some of these issues.</span></span>  
  
### <a name="consider-custom-property-editors-for-all-your-key-properties"></a><span data-ttu-id="6bc24-138">为所有关键属性考虑自定义属性编辑器</span><span class="sxs-lookup"><span data-stu-id="6bc24-138">Consider Custom Property Editors for all Your Key Properties</span></span>  
 <span data-ttu-id="6bc24-139">就无法将基于属性的重要的属性验证放在属性表中。</span><span class="sxs-lookup"><span data-stu-id="6bc24-139">It is impossible to put significant property validation on top of properties in the property sheet.</span></span> <span data-ttu-id="6bc24-140">框架尝试使用 XML 架构定义 (XSD) 的 simpleType 限制来定义 UI 的验证规则。</span><span class="sxs-lookup"><span data-stu-id="6bc24-140">The framework attempts to use XML Schema Definition (XSD) simpleType restrictions to define the validation rules for the UI.</span></span> <span data-ttu-id="6bc24-141">最大和最小值的简单规则会应用，但不是支持字符串字段的正则表达式限制。</span><span class="sxs-lookup"><span data-stu-id="6bc24-141">The simple rules for maximum and minimum value are applied but the regular expression restriction for string fields is not supported.</span></span> <span data-ttu-id="6bc24-142">此外，数据被转换为公共语言运行时 (CLR) 类型之前应用了限制。</span><span class="sxs-lookup"><span data-stu-id="6bc24-142">Also, the data is converted into common language runtime (CLR) types before the restriction is applied.</span></span> <span data-ttu-id="6bc24-143">这意味着 UI 用户有时获取含义模糊的类型转换错误而不是超出范围错误。</span><span class="sxs-lookup"><span data-stu-id="6bc24-143">This means the user of the UI sometimes gets a cryptic type-conversion error rather than an out-of-range error.</span></span> <span data-ttu-id="6bc24-144">总而言之，验证逻辑是非常不可靠。</span><span class="sxs-lookup"><span data-stu-id="6bc24-144">All in all, the validation logic is very weak.</span></span>  
  
 <span data-ttu-id="6bc24-145">很多适配器开发人员都采纳的解决方案是在属性页上编写自定义属性编辑器中提供的主要属性。</span><span class="sxs-lookup"><span data-stu-id="6bc24-145">The solution many adapter developers have adopted is to write custom property editors for the main properties on their property sheet.</span></span> <span data-ttu-id="6bc24-146">如果有大量相互依存的属性 （如通常都是如此），然后自定义属性编辑器可以将结果合并到单个字段，并在运行时更高版本可以，分隔它们。</span><span class="sxs-lookup"><span data-stu-id="6bc24-146">If there are a number of cross-dependent properties (as is often the case), then the custom property editor can combine the results into a single field and the runtime can later separate them.</span></span> <span data-ttu-id="6bc24-147">这是在界面获取必要的 （尽管一般来说是微不足道的） 自定义代码的唯一方法。</span><span class="sxs-lookup"><span data-stu-id="6bc24-147">This is the only way to get the necessary (though still generally trivial) custom code into the interface.</span></span>  
  
 <span data-ttu-id="6bc24-148">自定义属性编辑器的编写相对简单，可以批注 XSD 中的属性来使用它们。</span><span class="sxs-lookup"><span data-stu-id="6bc24-148">Custom property editors are relatively straightforward to write and the property in the XSD can be annotated to use them.</span></span> <span data-ttu-id="6bc24-149">批注引用的程序集公开的属性编辑器入口点，并通过编码来显示 CLR 窗体。</span><span class="sxs-lookup"><span data-stu-id="6bc24-149">The annotation references an assembly that exposes the property editor entry point, and it is coded to show a CLR Form.</span></span> <span data-ttu-id="6bc24-150">你现在可以编写常规用户界面，并使用 Visual Studio 提供的传统界面生成工具。</span><span class="sxs-lookup"><span data-stu-id="6bc24-150">You can now write a regular user interface and use the traditional interface-generation tools that Visual Studio offers.</span></span>  
  
 <span data-ttu-id="6bc24-151">下面的代码演示如何使用 XSD 添加一个自定义属性编辑器：</span><span class="sxs-lookup"><span data-stu-id="6bc24-151">The following code shows how to use the XSD to add a custom property editor:</span></span>  
  
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
  
 <span data-ttu-id="6bc24-152">引用的代码应如下所示：</span><span class="sxs-lookup"><span data-stu-id="6bc24-152">The code that is referenced should look like this:</span></span>  
  
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
  
 <span data-ttu-id="6bc24-153">管理运行时必须能够找到引用在 XSD 中，因此应将其添加到全局程序集缓存的程序集。</span><span class="sxs-lookup"><span data-stu-id="6bc24-153">The administration runtime must be able to find the assembly referenced in the XSD, so you should add it to the global assembly cache.</span></span>