---
title: "静态适配器 IStaticAdapterConfig 接口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 52f5de01-0cfc-456a-a52b-28f8f076bdfc
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2de8d95ba4a5945cb43e3681055750cdad628759
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="static-adapter-istaticadapterconfig-interface"></a><span data-ttu-id="ebf3c-102">静态适配器 IStaticAdapterConfig 接口</span><span class="sxs-lookup"><span data-stu-id="ebf3c-102">Static Adapter IStaticAdapterConfig Interface</span></span>
<span data-ttu-id="ebf3c-103">静态的设计时适配器必须实现**IStaticAdapterConfig**接口。</span><span class="sxs-lookup"><span data-stu-id="ebf3c-103">A static design-time adapter must implement the **IStaticAdapterConfig** interface.</span></span> <span data-ttu-id="ebf3c-104">这使得它可以与“添加适配器元数据向导”进行交互，并从适配器获得服务组织和各个服务的说明。</span><span class="sxs-lookup"><span data-stu-id="ebf3c-104">This allows it to interact with the Add Adapter Metadata Wizard and obtain service organizations and individual service descriptions from the adapter.</span></span> <span data-ttu-id="ebf3c-105">在向导调用**GetServiceOrganization**和**GetServiceDescription**方法中拉入适配器与之交互的元数据信息并将其添加到 BizTalk 项目中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ebf3c-105">The wizard calls the **GetServiceOrganization** and **GetServiceDescription** methods to pull in metadata information with which the adapter interacts and add it to a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
 <span data-ttu-id="ebf3c-106">**GetServiceOrganization**方法获取表示适配器的公开服务的分层组织的 XML 实例文档。</span><span class="sxs-lookup"><span data-stu-id="ebf3c-106">The **GetServiceOrganization** method obtains an XML instance document that represents the hierarchical organization of the adapter's exposed services.</span></span> <span data-ttu-id="ebf3c-107">此结构生成，请参阅上的服务组织树**选择服务添加到导入**添加适配器元数据向导页。</span><span class="sxs-lookup"><span data-stu-id="ebf3c-107">This structure generates the service organization tree that you see on the **Select Services to Import** page in the Add Adapter Metadata Wizard.</span></span>  
  
 <span data-ttu-id="ebf3c-108">选择要导入的服务后，向导会调用**GetServiceDescription**方法来获取数组中添加已选定的服务类别所对应的 Web 服务描述语言 (WSDL) 文件适配器元数据向导树。</span><span class="sxs-lookup"><span data-stu-id="ebf3c-108">After you select the services to import, the wizard calls the **GetServiceDescription** method to obtain an array of Web Services Description Language (WSDL) files corresponding to the service categories that were selected in the Add Adapter Metadata Wizard tree.</span></span> <span data-ttu-id="ebf3c-109">完成“添加适配器元数据向导”后，代表这些服务的架构将生成为 XSD 文件，并添加到 BizTalk 项目中。</span><span class="sxs-lookup"><span data-stu-id="ebf3c-109">Schemas representing the services are generated as XSD files and added to your BizTalk project after you complete the Add Adapter Metadata Wizard.</span></span>  
  
 <span data-ttu-id="ebf3c-110">在文件适配器示例中， **GetServiceOrganization**和**GetServiceDescription**方法驻留在**StaticAdapterManagement**类AdapterManagement.cs 类文件。</span><span class="sxs-lookup"><span data-stu-id="ebf3c-110">In the file adapter sample, the **GetServiceOrganization** and **GetServiceDescription** methods reside in the **StaticAdapterManagement** class in the AdapterManagement.cs class file.</span></span> <span data-ttu-id="ebf3c-111">在向导调用**GetServiceOrganization**方法来获取树结构来显示上**选择服务添加到导入**页。</span><span class="sxs-lookup"><span data-stu-id="ebf3c-111">The wizard calls the **GetServiceOrganization** method to obtain the tree structure to display on the **Select Services to Import** page.</span></span> <span data-ttu-id="ebf3c-112">在**GetServicesOrganization**硬编码返回 AdapterManagement.CategorySchema.xml 文件值使用下面的代码段中所示。</span><span class="sxs-lookup"><span data-stu-id="ebf3c-112">In **GetServicesOrganization** the hard-coded return value of AdapterManagement.CategorySchema.xml file is used as shown in the following code fragment.</span></span> <span data-ttu-id="ebf3c-113">作为适配器开发人员，您需要添加逻辑以返回相应的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="ebf3c-113">As an adapter developer you will need to add the logic to return the appropriate XML file.</span></span>  
  
```  
public string GetServiceOrganization(IPropertyBag endPointConfiguration, string NodeIdentifier)   
{  
   string result = GetResource("AdapterManagement.CategorySchema.xml");  
   return result;  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="ebf3c-114">请确保修改**GetServiceDescription**方法**StaticAdapterManagement**类，而不**DynamicAdapterManagement**类，该类中第一个出现该文件。</span><span class="sxs-lookup"><span data-stu-id="ebf3c-114">Be sure to modify the **GetServiceDescription** method of the **StaticAdapterManagement** class, and not of the **DynamicAdapterManagement** class, which appears first in the file.</span></span>  
  
 <span data-ttu-id="ebf3c-115">下面的代码是从**GetServiceDescription** AdapterManagement.cs 文件的方法。</span><span class="sxs-lookup"><span data-stu-id="ebf3c-115">The following code is from the **GetServiceDescription** method of the AdapterManagement.cs file.</span></span> <span data-ttu-id="ebf3c-116">service1.wsdl 文件硬编码为返回的 WSDL 文件。</span><span class="sxs-lookup"><span data-stu-id="ebf3c-116">The file service1.wsdl is hard-coded as the WSDL file returned.</span></span> <span data-ttu-id="ebf3c-117">它返回以 WSDL 文件表示的架构。</span><span class="sxs-lookup"><span data-stu-id="ebf3c-117">It returns schemas represented as WSDL files.</span></span> <span data-ttu-id="ebf3c-118">`wsdls`参数是数组的对应于源加载的 XML 中的 WSDL 引用的唯一 WSDL 引用**GetServicesOrganization**。</span><span class="sxs-lookup"><span data-stu-id="ebf3c-118">The `wsdls` parameter is an array of unique WSDL references that correspond to the WSDL references in the source XML loaded by **GetServicesOrganization**.</span></span> <span data-ttu-id="ebf3c-119">返回的 WSDL 说明的集合用于生成 BizTalk 项目的端口类型和消息类型。</span><span class="sxs-lookup"><span data-stu-id="ebf3c-119">The returned set of WSDL descriptions are used to generate the port types and message types for the BizTalk project.</span></span> <span data-ttu-id="ebf3c-120">如果树中有多个可选的架构类型，则需要多个 WSDL 文件。</span><span class="sxs-lookup"><span data-stu-id="ebf3c-120">If you have more than one schema type available for selection in the tree, you will need more than one WSDL file.</span></span> <span data-ttu-id="ebf3c-121">如果有多种可能的架构和 WSDL 选择，则可能需要添加数据库查找才能返回正确的 WSDL 文件。</span><span class="sxs-lookup"><span data-stu-id="ebf3c-121">If you have many possible schema and WSDL choices, you may want to add a database lookup to return the correct WSDL file.</span></span>  
  
```  
/// <summary>     
        /// Get the WSDL file name for the selected WSDL  
        /// </summary>  
        /// <param name="wsdls">place holder</param>  
        /// <returns>An empty string[]</returns>  
        public string[] GetServiceDescription(string[] wsdls)   
      {  
            string[] result = new string[1];  
            result[0] = GetResource("AdapterManagement.service1.wsdl");  
            return result;  
        }  
```  
  
## <a name="see-also"></a><span data-ttu-id="ebf3c-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ebf3c-122">See Also</span></span>  
 [<span data-ttu-id="ebf3c-123">静态的设计时适配器配置</span><span class="sxs-lookup"><span data-stu-id="ebf3c-123">Static Design-Time Adapter Configuration</span></span>](../core/static-design-time-adapter-configuration.md)