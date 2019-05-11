---
title: 如何添加 Namespace 示例工作原理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c76a90a9-5898-43b3-98af-ff546dd97153
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dccb5aebb19895e05ed424f64b4f2ba431174f6d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397112"
---
# <a name="how-the-add-namespace-sample-works"></a>如何添加 Namespace 示例能够正常工作
第一，第二和第四个测试使用**添加 Namespace**组件位于 NamespaceSampleReceivePipeline 管道中。 它将作为输入具有对根节点，如下所示没有命名空间的文档：  

```  
<CanonicalOrder OrderID="OrderID_0" OrderDate="OrderDate_1" Status="Status_2">  
```  

 下表显示了设置的属性值**添加 Namespace**组件。  


|      属性       |  类型   |                          ReplTest1                           |
|---------------------|---------|----------------------------------------------------------|
| ExtractionNodeXPath | Static  |                         （空）                          |
|    NamespaceBase    | Static  |    http://schemas.microsoft.biztalk.esb.test.com/test    |
|   NamespacePrefix   | Static  |                         esbTest                          |
|      Separator      | Static  |                            /                             |
|       Xpath        | 动态 | /CanonicalOrder/@OrderID&#124;/CanonicalOrder/@OrderDate |

 表中显示的属性设置会导致要通过执行两个 XPath 查询来搜索 XML 文档的组件/CanonicalOrder/@OrderID并/CanonicalOrder/@OrderDate(为指定的两个查询**Xpath**分隔"管道"属性字符）。 这些查询返回的值**OrderID**并**OrderDate**属性的根节点的文档; 在此示例中，两个值是"OrderID_0"和"OrderDate_1"。  

 该组件然后使用这些值和其他属性的值来构造新的根命名空间。 它将结合**NamespaceBase**，则**NamespacePrefix**，则**分隔符**，以及采用以下格式的两个 XPath 查询中的值：  

```  
xmlns:{NamespacePrefix}="{NamespaceBase}{Separator}{XPaths[1]}{Seperator}  
                         {XPaths[2]}{Separator}...{XPaths[n]}"  
```  

 这会生成新的命名空间，如下所示：  

```  
xmlns:esbTest="http://schemas.microsoft.biztalk.esb.test.com/test  
               /OrderID_0/OrderDate_1"  
```  

 因此，更新后的文档的处理后**NamespaceSampleReceivePipeline**管道是以下：  

```  
<esbTest:CanonicalOrder xmlns:esbTest=  
    "http://schemas.microsoft.biztalk.esb.test.com/test/OrderID_0  
    /OrderDate_1" OrderID="OrderID_0" OrderDate="OrderDate_1"   
    Status="Status_2">  
```  

## <a name="using-the-extractionnodexpath-property"></a>使用 ExtractionNodeXPath 属性  
 默认情况下**添加 Namespace**组件添加命名空间和前缀信息时使用的消息中的 XML 文档的根元素。 如果你想要使用的 XML 文档的一个子集作为消息正文 （在某些方案中信封或仅为一部分的入站文档具有相关性的情况下很有用），则可以设置**ExtractionNodeXPath**属性强制**添加 Namespace**组件以查找用于生成消息的指定的元素。 例如，如果您知道，收到的 CanonicalOrder 消息将仅包含一个**OrderDetails**适用于它所包含的此消息的使用者的元素，可以设置**ExtractionNodeXPath**属性指定的路径**OrderDetails**元素。 可以看到此过程中添加通过提取到直通测试前面所述的示例。  

> [!NOTE]
>  **ExtractionNodeXPath**属性必须返回只有一个元素的 XPath。 如果结果不是一个元素或 XPath 查询返回多个元素，该组件会引发异常。