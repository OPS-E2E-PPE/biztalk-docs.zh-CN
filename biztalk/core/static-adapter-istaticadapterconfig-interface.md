---
title: 静态适配器 IStaticAdapterConfig 接口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 52f5de01-0cfc-456a-a52b-28f8f076bdfc
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 296520f7f879e45657c6559827387239d7e10fe0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392869"
---
# <a name="static-adapter-istaticadapterconfig-interface"></a><span data-ttu-id="1960b-102">静态适配器 IStaticAdapterConfig 接口</span><span class="sxs-lookup"><span data-stu-id="1960b-102">Static Adapter IStaticAdapterConfig Interface</span></span>
<span data-ttu-id="1960b-103">静态设计时适配器必须实现**IStaticAdapterConfig**接口。</span><span class="sxs-lookup"><span data-stu-id="1960b-103">A static design-time adapter must implement the **IStaticAdapterConfig** interface.</span></span> <span data-ttu-id="1960b-104">这使得它可以交互使用添加适配器元数据向导，并从适配器获取服务组织和各个服务的说明。</span><span class="sxs-lookup"><span data-stu-id="1960b-104">This allows it to interact with the Add Adapter Metadata Wizard and obtain service organizations and individual service descriptions from the adapter.</span></span> <span data-ttu-id="1960b-105">该向导调用**GetServiceOrganization**并**GetServiceDescription**方法来提取该适配器与之进行交互的元数据信息并将其添加到 BizTalk 项目中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1960b-105">The wizard calls the **GetServiceOrganization** and **GetServiceDescription** methods to pull in metadata information with which the adapter interacts and add it to a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
 <span data-ttu-id="1960b-106">**GetServiceOrganization**方法中获取代表适配器的公开的服务的分层组织的 XML 实例文档。</span><span class="sxs-lookup"><span data-stu-id="1960b-106">The **GetServiceOrganization** method obtains an XML instance document that represents the hierarchical organization of the adapter's exposed services.</span></span> <span data-ttu-id="1960b-107">此结构生成，请参阅的服务组织树**选择导入的服务**添加适配器元数据向导中的页。</span><span class="sxs-lookup"><span data-stu-id="1960b-107">This structure generates the service organization tree that you see on the **Select Services to Import** page in the Add Adapter Metadata Wizard.</span></span>  
  
 <span data-ttu-id="1960b-108">该向导选择要导入的服务后，调用**GetServiceDescription**方法来获取数组中添加处于选中状态的服务类别相对应的 Web 服务描述语言 (WSDL) 文件适配器元数据向导树。</span><span class="sxs-lookup"><span data-stu-id="1960b-108">After you select the services to import, the wizard calls the **GetServiceDescription** method to obtain an array of Web Services Description Language (WSDL) files corresponding to the service categories that were selected in the Add Adapter Metadata Wizard tree.</span></span> <span data-ttu-id="1960b-109">架构表示的服务生成为 XSD 文件，并在完成添加适配器元数据向导后添加到 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="1960b-109">Schemas representing the services are generated as XSD files and added to your BizTalk project after you complete the Add Adapter Metadata Wizard.</span></span>  
  
 <span data-ttu-id="1960b-110">在文件适配器示例中， **GetServiceOrganization**并**GetServiceDescription**方法驻留**StaticAdapterManagement**类AdapterManagement.cs 类文件。</span><span class="sxs-lookup"><span data-stu-id="1960b-110">In the file adapter sample, the **GetServiceOrganization** and **GetServiceDescription** methods reside in the **StaticAdapterManagement** class in the AdapterManagement.cs class file.</span></span> <span data-ttu-id="1960b-111">该向导调用**GetServiceOrganization**方法来获取上显示的树结构**选择导入的服务**页。</span><span class="sxs-lookup"><span data-stu-id="1960b-111">The wizard calls the **GetServiceOrganization** method to obtain the tree structure to display on the **Select Services to Import** page.</span></span> <span data-ttu-id="1960b-112">在中**GetServicesOrganization**硬编码返回 AdapterManagement.CategorySchema.xml 文件的值使用下面的代码段中所示。</span><span class="sxs-lookup"><span data-stu-id="1960b-112">In **GetServicesOrganization** the hard-coded return value of AdapterManagement.CategorySchema.xml file is used as shown in the following code fragment.</span></span> <span data-ttu-id="1960b-113">作为适配器开发人员将需要添加逻辑以返回相应的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="1960b-113">As an adapter developer you will need to add the logic to return the appropriate XML file.</span></span>  
  
```  
public string GetServiceOrganization(IPropertyBag endPointConfiguration, string NodeIdentifier)   
{  
   string result = GetResource("AdapterManagement.CategorySchema.xml");  
   return result;  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="1960b-114">确保修改**GetServiceDescription**方法**StaticAdapterManagement**类，而不是**DynamicAdapterManagement**类，该类中第一个出现该文件。</span><span class="sxs-lookup"><span data-stu-id="1960b-114">Be sure to modify the **GetServiceDescription** method of the **StaticAdapterManagement** class, and not of the **DynamicAdapterManagement** class, which appears first in the file.</span></span>  
  
 <span data-ttu-id="1960b-115">以下代码摘自**GetServiceDescription** AdapterManagement.cs 文件的方法。</span><span class="sxs-lookup"><span data-stu-id="1960b-115">The following code is from the **GetServiceDescription** method of the AdapterManagement.cs file.</span></span> <span data-ttu-id="1960b-116">Service1.wsdl 文件是硬编码为返回的 WSDL 文件。</span><span class="sxs-lookup"><span data-stu-id="1960b-116">The file service1.wsdl is hard-coded as the WSDL file returned.</span></span> <span data-ttu-id="1960b-117">它将返回以 WSDL 文件表示的架构。</span><span class="sxs-lookup"><span data-stu-id="1960b-117">It returns schemas represented as WSDL files.</span></span> <span data-ttu-id="1960b-118">`wsdls`参数是唯一对应于源加载的 XML 中的 WSDL 引用的 WSDL 引用的数组**GetServicesOrganization**。</span><span class="sxs-lookup"><span data-stu-id="1960b-118">The `wsdls` parameter is an array of unique WSDL references that correspond to the WSDL references in the source XML loaded by **GetServicesOrganization**.</span></span> <span data-ttu-id="1960b-119">返回的组的 WSDL 说明用于生成的端口类型和消息类型的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="1960b-119">The returned set of WSDL descriptions are used to generate the port types and message types for the BizTalk project.</span></span> <span data-ttu-id="1960b-120">如果在树中有多个可供选择的架构类型，则需要多个 WSDL 文件。</span><span class="sxs-lookup"><span data-stu-id="1960b-120">If you have more than one schema type available for selection in the tree, you will need more than one WSDL file.</span></span> <span data-ttu-id="1960b-121">如果您有许多可能的架构和 WSDL 选择，你可能想要添加数据库查找才能返回正确的 WSDL 文件。</span><span class="sxs-lookup"><span data-stu-id="1960b-121">If you have many possible schema and WSDL choices, you may want to add a database lookup to return the correct WSDL file.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1960b-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="1960b-122">See Also</span></span>  
 [<span data-ttu-id="1960b-123">静态设计时适配器配置</span><span class="sxs-lookup"><span data-stu-id="1960b-123">Static Design-Time Adapter Configuration</span></span>](../core/static-design-time-adapter-configuration.md)