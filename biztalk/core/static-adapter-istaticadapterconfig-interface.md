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
# <a name="static-adapter-istaticadapterconfig-interface"></a>静态适配器 IStaticAdapterConfig 接口
静态的设计时适配器必须实现**IStaticAdapterConfig**接口。 这使得它可以与“添加适配器元数据向导”进行交互，并从适配器获得服务组织和各个服务的说明。 在向导调用**GetServiceOrganization**和**GetServiceDescription**方法中拉入适配器与之交互的元数据信息并将其添加到 BizTalk 项目中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
  
 **GetServiceOrganization**方法获取表示适配器的公开服务的分层组织的 XML 实例文档。 此结构生成，请参阅上的服务组织树**选择服务添加到导入**添加适配器元数据向导页。  
  
 选择要导入的服务后，向导会调用**GetServiceDescription**方法来获取数组中添加已选定的服务类别所对应的 Web 服务描述语言 (WSDL) 文件适配器元数据向导树。 完成“添加适配器元数据向导”后，代表这些服务的架构将生成为 XSD 文件，并添加到 BizTalk 项目中。  
  
 在文件适配器示例中， **GetServiceOrganization**和**GetServiceDescription**方法驻留在**StaticAdapterManagement**类AdapterManagement.cs 类文件。 在向导调用**GetServiceOrganization**方法来获取树结构来显示上**选择服务添加到导入**页。 在**GetServicesOrganization**硬编码返回 AdapterManagement.CategorySchema.xml 文件值使用下面的代码段中所示。 作为适配器开发人员，您需要添加逻辑以返回相应的 XML 文件。  
  
```  
public string GetServiceOrganization(IPropertyBag endPointConfiguration, string NodeIdentifier)   
{  
   string result = GetResource("AdapterManagement.CategorySchema.xml");  
   return result;  
}  
```  
  
> [!NOTE]
>  请确保修改**GetServiceDescription**方法**StaticAdapterManagement**类，而不**DynamicAdapterManagement**类，该类中第一个出现该文件。  
  
 下面的代码是从**GetServiceDescription** AdapterManagement.cs 文件的方法。 service1.wsdl 文件硬编码为返回的 WSDL 文件。 它返回以 WSDL 文件表示的架构。 `wsdls`参数是数组的对应于源加载的 XML 中的 WSDL 引用的唯一 WSDL 引用**GetServicesOrganization**。 返回的 WSDL 说明的集合用于生成 BizTalk 项目的端口类型和消息类型。 如果树中有多个可选的架构类型，则需要多个 WSDL 文件。 如果有多种可能的架构和 WSDL 选择，则可能需要添加数据库查找才能返回正确的 WSDL 文件。  
  
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
  
## <a name="see-also"></a>另请参阅  
 [静态的设计时适配器配置](../core/static-design-time-adapter-configuration.md)