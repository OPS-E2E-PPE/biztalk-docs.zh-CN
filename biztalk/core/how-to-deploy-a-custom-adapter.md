---
title: "如何部署自定义适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f17b336c-6232-4889-ab7e-92b83fab0f5f
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e36443b99f01688a38e66a4a302ab64bb220092f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-deploy-a-custom-adapter"></a><span data-ttu-id="e74fd-102">如何部署自定义适配器</span><span class="sxs-lookup"><span data-stu-id="e74fd-102">How to Deploy a Custom Adapter</span></span>
<span data-ttu-id="e74fd-103">一个完整的适配器安装过程包括以下步骤：</span><span class="sxs-lookup"><span data-stu-id="e74fd-103">A complete adapter installation process consists of the following steps:</span></span>  
  
1.  <span data-ttu-id="e74fd-104">检查依存关系。</span><span class="sxs-lookup"><span data-stu-id="e74fd-104">Check dependencies.</span></span> <span data-ttu-id="e74fd-105">例如，MSMQ 适配器安装程序检查本地是否存在 MSMQ 服务，因为该适配器运行时依赖此服务。</span><span class="sxs-lookup"><span data-stu-id="e74fd-105">For example, the MSMQ adapter installer checks for the existence of the local MSMQ service because the adapter runtime depends on it.</span></span>  
  
2.  <span data-ttu-id="e74fd-106">设置本地文件系统。</span><span class="sxs-lookup"><span data-stu-id="e74fd-106">Set up the local file system.</span></span> <span data-ttu-id="e74fd-107">这包括创建安装文件夹以及复制二进制文件和支持文件。</span><span class="sxs-lookup"><span data-stu-id="e74fd-107">This includes creating installation folders and copying binary and support files.</span></span> <span data-ttu-id="e74fd-108">确保文件夹和文件访问权限配置正确。</span><span class="sxs-lookup"><span data-stu-id="e74fd-108">Ensure access to folders and file access permissions are configured properly.</span></span>  
  
3.  <span data-ttu-id="e74fd-109">将托管程序集安装在系统全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="e74fd-109">Install managed assemblies into the system global assembly cache.</span></span>  
  
4.  <span data-ttu-id="e74fd-110">创建适配器的注册表项。</span><span class="sxs-lookup"><span data-stu-id="e74fd-110">Create registry keys for the adapter.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e74fd-111">对于 32 位适配器，BizTalk Server 管理控制台使用注册表中的 HKEY_CLASSES_ROOT 分支获取自定义适配器配置。</span><span class="sxs-lookup"><span data-stu-id="e74fd-111">For a 32-bit adapter, the BizTalk Server Administration Console uses the HKEY_CLASSES_ROOT branch in the registry to obtain custom adapter configuration.</span></span>  <span data-ttu-id="e74fd-112">如果在 64 位服务器上安装 32 位适配器，则 BizTalk Serve 管理控制台使用 HKEY_CLASSES_ROOT\Wow6432Node\ 分支获取适配器配置数据。</span><span class="sxs-lookup"><span data-stu-id="e74fd-112">If a 32-bit adapter is installed on a 64-bit server, the BizTalk Serve Administration Console instead uses the HKEY_CLASSES_ROOT\Wow6432Node\ branch for adapter configuration data.</span></span>  
  
5.  <span data-ttu-id="e74fd-113">将适配器添加到 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="e74fd-113">Add the adapter to BizTalk Server.</span></span> <span data-ttu-id="e74fd-114">这意味着在 BizTalk 管理数据库中为适配器以及为用于反映适配器所升级的属性的属性架构添加新条目。</span><span class="sxs-lookup"><span data-stu-id="e74fd-114">This means new entries in the BizTalk Management database for the adapter as well as for the property schema used to reflect properties the adapter promotes.</span></span> <span data-ttu-id="e74fd-115">有时会使用 BizTalk Server 管理控制台手动完成此步骤。</span><span class="sxs-lookup"><span data-stu-id="e74fd-115">This step is sometimes done manually using the BizTalk Server Administration console.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="e74fd-116">异常</span><span class="sxs-lookup"><span data-stu-id="e74fd-116">Exceptions</span></span>  
 <span data-ttu-id="e74fd-117">在进行 BizTalk Server 的非完整安装时，适配器安装程序可能不需要检查依存关系。</span><span class="sxs-lookup"><span data-stu-id="e74fd-117">The adapter installer may not need to check the dependencies in partial BizTalk Server installations.</span></span> <span data-ttu-id="e74fd-118">例如，在仅安装管理工具时，适配器安装程序不需要检查适配器运行时依存关系，因为不使用适配器运行时。</span><span class="sxs-lookup"><span data-stu-id="e74fd-118">For example, in an administration tools-only installation, the adapter installer does not need to check adapter runtime dependencies because the adapter runtime is not used.</span></span> <span data-ttu-id="e74fd-119">同样，在仅安装 BizTalk Server 运行时的时候，适配器安装程序也不需要检查适配器设计时依存关系。</span><span class="sxs-lookup"><span data-stu-id="e74fd-119">The same is true in the BizTalk Server runtime-only installation, where the adapter installer does not need to check the adapter design-time dependencies.</span></span>  
  
 <span data-ttu-id="e74fd-120">在多 BizTalk Server 环境中，前面所列步骤中的最后一步（将适配器添加到 BizTalk Server）仅当在第一个 BizTalk Server 上安装适配器时才需要。</span><span class="sxs-lookup"><span data-stu-id="e74fd-120">In multiple BizTalk Server environments, the last step in the preceding list (Add the adapter to BizTalk Server) only happens in the adapter installation on the first BizTalk Server.</span></span> <span data-ttu-id="e74fd-121">这是因为所有 BizTalk Server 服务实例都共享同一个 BizTalk 管理数据库（默认名称为 BizTalkMgmtDB）。</span><span class="sxs-lookup"><span data-stu-id="e74fd-121">This is because all BizTalk Server service instances share the same BizTalk Management database (with the default name, BizTalkMgmtDB).</span></span> <span data-ttu-id="e74fd-122">如果将适配器添加到同组的其他 BizTalk 服务器中，则这些附加的安装步骤会失败。</span><span class="sxs-lookup"><span data-stu-id="e74fd-122">If adapters are added to other BizTalk servers in the same group, the additional steps fail.</span></span>  
  
## <a name="install-the-adapter-assemblies-into-the-global-assembly-cache"></a><span data-ttu-id="e74fd-123">将适配器程序集安装在全局程序集缓存中</span><span class="sxs-lookup"><span data-stu-id="e74fd-123">Install the Adapter Assemblies into the Global Assembly Cache</span></span>  
 <span data-ttu-id="e74fd-124">为了支持具有不同适配器安装路径的多 BizTalk Server 主机环境，必须将适配器程序集安装在系统全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="e74fd-124">To support multiple BizTalk Server host environments with different adapter installation paths, the adapter assemblies must be installed into the system global assembly cache.</span></span>  
  
 <span data-ttu-id="e74fd-125">在适配器安装和配置过程中，会在 BizTalk 管理数据库（默认名称为 BizTalkMgmtDB）的 adm_adapter 表中创建一个新适配器条目。</span><span class="sxs-lookup"><span data-stu-id="e74fd-125">During the adapter installation and configuration, a new adapter entry is created in the adm_adapter table of the BizTalk Management database (with the default name BizTalkMgmtDB).</span></span> <span data-ttu-id="e74fd-126">此条目包含 BizTalk Server 运行时和设计时使用的所有引用信息。</span><span class="sxs-lookup"><span data-stu-id="e74fd-126">This entry contains all reference information used by BizTalk Server for both run time and design time.</span></span>  
  
 <span data-ttu-id="e74fd-127">**InBoundAssemblyPath**和**OutboundAssemblyPath**字段由 BizTalk Server 运行时，若要了解加载适配器二进制文件的位置。</span><span class="sxs-lookup"><span data-stu-id="e74fd-127">The **InBoundAssemblyPath** and **OutboundAssemblyPath** fields are used by the BizTalk Server runtime to find out where to load the adapter binaries.</span></span> <span data-ttu-id="e74fd-128">因为一个 BizTalk Server 组只有一个 BizTalk 管理数据库，所以组中的所有 BizTalk 服务器必须共享这同一条信息。</span><span class="sxs-lookup"><span data-stu-id="e74fd-128">Because there is only one BizTalk Management database for a BizTalk Server group, all BizTalk servers in the group must share this same piece of information.</span></span> <span data-ttu-id="e74fd-129">如果要将适配器安装在组内的不同 BizTalk 服务器上，则必须在每台这样的服务器上都使用同一条安装路径。</span><span class="sxs-lookup"><span data-stu-id="e74fd-129">If you want to install the adapter on different BizTalk servers within the group, you must use the same installation path on each of those servers.</span></span> <span data-ttu-id="e74fd-130">如果本地安装路径与 BizTalk 管理数据库存储的路径不同，则 BizTalk Server 无法加载适配器二进制文件。</span><span class="sxs-lookup"><span data-stu-id="e74fd-130">If the local installation path is different from the path stored in the BizTalk Management database, BizTalk Server cannot load the adapter binaries.</span></span>  
  
 <span data-ttu-id="e74fd-131">在适配器安装过程中，应始终用强名称签署适配器的程序集，并使用 Gacutil.exe 将适配器程序集放在系统全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="e74fd-131">Always sign the adapter's assembly with a strong name and use Gacutil.exe to put the adapter assembly into the system global assembly cache during the adapter installation.</span></span> <span data-ttu-id="e74fd-132">请确保你保留**InBoundAssemblyPath**和**OutboundAssemblyPath**字段为 null，或为空。</span><span class="sxs-lookup"><span data-stu-id="e74fd-132">Make sure that you leave the **InBoundAssemblyPath** and **OutboundAssemblyPath** fields null, or empty.</span></span>  
  
## <a name="using-the-framework-for-adapter-configuration"></a><span data-ttu-id="e74fd-133">使用适配器框架配置</span><span class="sxs-lookup"><span data-stu-id="e74fd-133">Using the Framework for Adapter Configuration</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="e74fd-134">为适配器配置用户界面 (UI) 提供对生成的属性表的机制。</span><span class="sxs-lookup"><span data-stu-id="e74fd-134"> provides a mechanism for generating property sheets for the adapter configuration user interface (UI).</span></span> <span data-ttu-id="e74fd-135">它基于配置属性的 XML 架构定义 (XSD) 所做的定义。</span><span class="sxs-lookup"><span data-stu-id="e74fd-135">It is based on an XML Schema Definition (XSD) definition of the configuration properties.</span></span> <span data-ttu-id="e74fd-136">使用此框架给适配器开发人员带来很大的挑战。</span><span class="sxs-lookup"><span data-stu-id="e74fd-136">The use of this framework introduces significant challenges for the adapter developer.</span></span> <span data-ttu-id="e74fd-137">本部分为应对其中的部分问题提供了有效的对策。</span><span class="sxs-lookup"><span data-stu-id="e74fd-137">This section suggests an effective workaround for some of these issues.</span></span>  
  
### <a name="consider-custom-property-editors-for-all-your-key-properties"></a><span data-ttu-id="e74fd-138">对所有关键属性考虑使用自定义属性编辑器</span><span class="sxs-lookup"><span data-stu-id="e74fd-138">Consider Custom Property Editors for all Your Key Properties</span></span>  
 <span data-ttu-id="e74fd-139">把重要的属性验证放在属性页的顶部属性中，是不可能的。</span><span class="sxs-lookup"><span data-stu-id="e74fd-139">It is impossible to put significant property validation on top of properties in the property sheet.</span></span> <span data-ttu-id="e74fd-140">框架尝试使用 XML 架构定义 (XSD) 的 simpleType 限制来定义 UI 的验证规则。</span><span class="sxs-lookup"><span data-stu-id="e74fd-140">The framework attempts to use XML Schema Definition (XSD) simpleType restrictions to define the validation rules for the UI.</span></span> <span data-ttu-id="e74fd-141">采用了简单的最大和最小值规则，但不支持字符串字段的正则表达式限制。</span><span class="sxs-lookup"><span data-stu-id="e74fd-141">The simple rules for maximum and minimum value are applied but the regular expression restriction for string fields is not supported.</span></span> <span data-ttu-id="e74fd-142">另外，在应用限制之前，数据被转换为公共语言运行时 (CLR) 类型。</span><span class="sxs-lookup"><span data-stu-id="e74fd-142">Also, the data is converted into common language runtime (CLR) types before the restriction is applied.</span></span> <span data-ttu-id="e74fd-143">这意味着 UI 用户有时会收到加密的类型转换错误，而不会收到越界错误。</span><span class="sxs-lookup"><span data-stu-id="e74fd-143">This means the user of the UI sometimes gets a cryptic type-conversion error rather than an out-of-range error.</span></span> <span data-ttu-id="e74fd-144">总而言之，验证逻辑很弱。</span><span class="sxs-lookup"><span data-stu-id="e74fd-144">All in all, the validation logic is very weak.</span></span>  
  
 <span data-ttu-id="e74fd-145">很多适配器开发人员都采纳的解决方案是，为属性页的主要属性编写自定义属性编辑器。</span><span class="sxs-lookup"><span data-stu-id="e74fd-145">The solution many adapter developers have adopted is to write custom property editors for the main properties on their property sheet.</span></span> <span data-ttu-id="e74fd-146">如果有很多相互依存的属性（通常会是这种情况），则自定义属性编辑器可以将结果合并到单个字段中，以后运行时可以将这些结果分开。</span><span class="sxs-lookup"><span data-stu-id="e74fd-146">If there are a number of cross-dependent properties (as is often the case), then the custom property editor can combine the results into a single field and the runtime can later separate them.</span></span> <span data-ttu-id="e74fd-147">这是将必要的（尽管一般来说是微不足道的）自定义代码放入接口的唯一办法。</span><span class="sxs-lookup"><span data-stu-id="e74fd-147">This is the only way to get the necessary (though still generally trivial) custom code into the interface.</span></span>  
  
 <span data-ttu-id="e74fd-148">自定义属性编辑器的编写相对简单，对 XSD 中的属性做批注就可以使用自定义属性编辑器。</span><span class="sxs-lookup"><span data-stu-id="e74fd-148">Custom property editors are relatively straightforward to write and the property in the XSD can be annotated to use them.</span></span> <span data-ttu-id="e74fd-149">批注引用提供属性编辑器入口点的程序集，并通过编码显示为 CLR 窗体。</span><span class="sxs-lookup"><span data-stu-id="e74fd-149">The annotation references an assembly that exposes the property editor entry point, and it is coded to show a CLR Form.</span></span> <span data-ttu-id="e74fd-150">现在，您可以编写常规用户界面和使用 Visual Studio 提供的传统界面生成工具。</span><span class="sxs-lookup"><span data-stu-id="e74fd-150">You can now write a regular user interface and use the traditional interface-generation tools that Visual Studio offers.</span></span>  
  
 <span data-ttu-id="e74fd-151">以下代码显示如何使用 XSD 添加一个自定义属性编辑器：</span><span class="sxs-lookup"><span data-stu-id="e74fd-151">The following code shows how to use the XSD to add a custom property editor:</span></span>  
  
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
  
 <span data-ttu-id="e74fd-152">引用的代码应像下面这样：</span><span class="sxs-lookup"><span data-stu-id="e74fd-152">The code that is referenced should look like this:</span></span>  
  
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
  
 <span data-ttu-id="e74fd-153">由于必须让管理运行时能找到 XSD 中引用的程序集，因此应该将此程序集添加到全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="e74fd-153">The administration runtime must be able to find the assembly referenced in the XSD, so you should add it to the global assembly cache.</span></span>