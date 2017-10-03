---
title: "如何添加 Namespace 示例适用 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c76a90a9-5898-43b3-98af-ff546dd97153
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 212364030353001cae0589d4d7562641db4b77e6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-the-add-namespace-sample-works"></a>如何添加 Namespace 示例的工作机制
第一，第二和第四个测试使用**添加 Namespace**组件位于 NamespaceSampleReceivePipeline 管道。 它将作为输入具有根节点，如下所示上没有命名空间的文档：  
  
```  
<CanonicalOrder OrderID="OrderID_0" OrderDate="OrderDate_1" Status="Status_2">  
```  
  
 下表显示设置的属性值**添加 Namespace**组件。  
  
|属性|类型|值|  
|--------------|----------|-----------|  
|ExtractionNodeXPath|静态|（空）|  
|NamespaceBase|静态|http://schemas.microsoft.biztalk.esb.test.com/test|  
|NamespacePrefix|静态|esbTest|  
|分隔符|静态|/|  
|Xpath|Dynamic|/CanonicalOrder/@OrderID&#124;/CanonicalOrder/@OrderDate|  
  
 表所示的属性设置会导致将要通过执行两个 XPath 查询搜索 XML 文档的组件/CanonicalOrder/@OrderID和/CanonicalOrder/@OrderDate(为指定的两个查询**Xpath**属性，"管道"分隔字符）。 这些查询返回的值**OrderID**和**OrderDate**属性的根节点的文档; 在此示例中，两个值是"OrderID_0"和"OrderDate_1"。  
  
 组件然后使用这些值和其他属性时，值构造的新的根命名空间。 它整合了**NamespaceBase**、 **NamespacePrefix**、**分隔符**，以及采用以下格式的两个 XPath 查询中的值：  
  
```  
xmlns:{NamespacePrefix}="{NamespaceBase}{Separator}{XPaths[1]}{Seperator}  
                         {XPaths[2]}{Separator}...{XPaths[n]}"  
```  
  
 这将产生新的命名空间，如下所示：  
  
```  
xmlns:esbTest="http://schemas.microsoft.biztalk.esb.test.com/test  
               /OrderID_0/OrderDate_1"  
```  
  
 因此，在通过处理后的更新的文档**NamespaceSampleReceivePipeline**管道是在以下：  
  
```  
<esbTest:CanonicalOrder xmlns:esbTest=  
    "http://schemas.microsoft.biztalk.esb.test.com/test/OrderID_0  
    /OrderDate_1" OrderID="OrderID_0" OrderDate="OrderDate_1"   
    Status="Status_2">  
```  
  
## <a name="using-the-extractionnodexpath-property"></a>使用 ExtractionNodeXPath 属性  
 默认情况下，**添加 Namespace**组件添加命名空间和前缀信息时使用的消息中的 XML 文档的根元素。 如果你想要使用 XML 文档的一个子集作为消息正文 （在某些信封方案中，或仅为一部分的入站文档具有相关性的情况下很有用），则可以设置**ExtractionNodeXPath**属性以强制**添加 Namespace**组件要查找用于生成消息的指定的元素。 例如，如果你知道收到的 CanonicalOrder 消息将具有只有一个**OrderDetails**适用于其中包含此消息的使用者的元素，可以设置**ExtractionNodeXPath**属性指定的路径**OrderDetails**元素。 你可以看到举例说明中添加通过提取到前面所述的传递测试此过程。  
  
> [!NOTE]
>  **ExtractionNodeXPath**属性必须返回仅有一个元素的 XPath。 如果结果不是元素或 XPath 查询返回多个元素，该组件将引发的异常。