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
# <a name="static-adapter-istaticadapterconfig-interface"></a>静态适配器 IStaticAdapterConfig 接口
静态设计时适配器必须实现**IStaticAdapterConfig**接口。 这使得它可以交互使用添加适配器元数据向导，并从适配器获取服务组织和各个服务的说明。 该向导调用**GetServiceOrganization**并**GetServiceDescription**方法来提取该适配器与之进行交互的元数据信息并将其添加到 BizTalk 项目中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
  
 **GetServiceOrganization**方法中获取代表适配器的公开的服务的分层组织的 XML 实例文档。 此结构生成，请参阅的服务组织树**选择导入的服务**添加适配器元数据向导中的页。  
  
 该向导选择要导入的服务后，调用**GetServiceDescription**方法来获取数组中添加处于选中状态的服务类别相对应的 Web 服务描述语言 (WSDL) 文件适配器元数据向导树。 架构表示的服务生成为 XSD 文件，并在完成添加适配器元数据向导后添加到 BizTalk 项目。  
  
 在文件适配器示例中， **GetServiceOrganization**并**GetServiceDescription**方法驻留**StaticAdapterManagement**类AdapterManagement.cs 类文件。 该向导调用**GetServiceOrganization**方法来获取上显示的树结构**选择导入的服务**页。 在中**GetServicesOrganization**硬编码返回 AdapterManagement.CategorySchema.xml 文件的值使用下面的代码段中所示。 作为适配器开发人员将需要添加逻辑以返回相应的 XML 文件。  
  
```  
public string GetServiceOrganization(IPropertyBag endPointConfiguration, string NodeIdentifier)   
{  
   string result = GetResource("AdapterManagement.CategorySchema.xml");  
   return result;  
}  
```  
  
> [!NOTE]
>  确保修改**GetServiceDescription**方法**StaticAdapterManagement**类，而不是**DynamicAdapterManagement**类，该类中第一个出现该文件。  
  
 以下代码摘自**GetServiceDescription** AdapterManagement.cs 文件的方法。 Service1.wsdl 文件是硬编码为返回的 WSDL 文件。 它将返回以 WSDL 文件表示的架构。 `wsdls`参数是唯一对应于源加载的 XML 中的 WSDL 引用的 WSDL 引用的数组**GetServicesOrganization**。 返回的组的 WSDL 说明用于生成的端口类型和消息类型的 BizTalk 项目。 如果在树中有多个可供选择的架构类型，则需要多个 WSDL 文件。 如果您有许多可能的架构和 WSDL 选择，你可能想要添加数据库查找才能返回正确的 WSDL 文件。  
  
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
  
## <a name="see-also"></a>请参阅  
 [静态设计时适配器配置](../core/static-design-time-adapter-configuration.md)