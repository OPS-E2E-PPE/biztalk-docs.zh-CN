---
title: 嵌套 XML 消息信封 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e880cef1-4e73-4bce-a06e-8c4d23bc5a8c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46b0f505dd9ba7da71df1cb460f9c9a6610763d3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263837"
---
# <a name="nested-xml-message-envelopes"></a>嵌套 XML 消息信封
可以嵌套 XML 信封以创建复杂的文档结构。 嵌套的 XML 信封可以有两种格式（灵活格式和规范格式）。 以下示例显示了封装的文档的灵活格式，在该格式中，文档和信封（以粗体类型显示）可在封闭信封中的同一级别上出现。  
  
```  
<envelope1>  
    <document1/>    <envelope2>  
        <document2/>  
        <document3/>  
    </envelope2>    <document4/>  
</envelope1>  
```  
  
 以下示例显示了一个类似的实例消息，它符合封装的文档的规范格式，在该格式中，所有文档都在最内层信封中的同一级别上出现。  
  
```  
<envelope1>  
    <envelope2>  
        <document1/>  
        <document2/>  
        <document3/>  
        <document4/>  
    </envelope2>  
</envelope1>  
  
```  
  
 假定实例消息采用上述格式之一，则 XML 拆装器将生成 document1、document2、document3 和 document4。 上述各文档的消息上下文包括从相应文档升级的属性以及在各封闭信封内升级的属性。 下表显示了当属性升级在各种信封和文档的第一列中指定时，对于灵活格式和规范格式的示例，将包含在每个不自动换行的文档的消息上下文中的已升级属性。  
  
|指定的属性升级|为灵活格式示例生成的消息上下文属性|为规范格式示例生成的消息上下文属性|  
|-----------------------------------|---------------------------------------------------------------|----------------------------------------------------------------|  
|envelope1：p1<br /><br /> envelope2：p3<br /><br /> document1：p2<br /><br /> document2：p4 和 p5<br /><br /> document3：无升级<br /><br /> document4：无升级|document1：p1、p2<br /><br /> document2：p1、p3、p4、p5<br /><br /> document3：p1、p3<br /><br /> document4：p1|document1：p1、p2、p3<br /><br /> document2：p1、p3、p4、p5<br /><br /> document3：p1、p3<br /><br /> document4：p1、p3|  
  
## <a name="see-also"></a>另请参阅  
 [XML 消息包络线](../core/xml-message-envelopes.md)   
 [XML 消息的结构](../core/structure-of-an-xml-message.md)   
 [如何为包络线创建架构](../core/how-to-create-schemas-for-envelopes.md)