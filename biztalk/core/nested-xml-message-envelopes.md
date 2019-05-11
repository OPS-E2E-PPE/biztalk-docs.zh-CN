---
title: 嵌套 XML 消息信封 |Microsoft Docs
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
ms.openlocfilehash: b341930a30c8653cb2db378a24c6600f48de0891
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65263369"
---
# <a name="nested-xml-message-envelopes"></a>嵌套 XML 消息信封
可以嵌套 XML 信封以创建复杂的文档结构。 嵌套的 XML 信封可以有两种形式，灵活格式和规范。 下面的示例显示了封装的文档，在其文档和信封 （以粗体显示） 可以出现在封闭信封中的级别相同的灵活的窗体。  
  
```  
<envelope1>  
    <document1/>    <envelope2>  
        <document2/>  
        <document3/>  
    </envelope2>    <document4/>  
</envelope1>  
```  
  
 下面的示例显示了类似的实例消息，符合封装的文档，所有文档都显示在最内层信封中的相同级别的规范格式。  
  
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
  
 给定的实例消息中所述的窗体，XML 拆装器将生成 document1、 document2、 document3 和 document4。 每个文档的消息上下文包括从相应文档升级的属性，以及每个封闭信封内升级的属性。 下表显示了这两种灵活和规范格式示例中，在各种信封的第一列中指定属性升级每个未包装文档的消息上下文中包括的已升级的属性将成为和文档数。  
  
|指定的属性升级|灵活格式示例的生成的消息上下文属性|规范格式示例的生成的消息上下文属性|  
|-----------------------------------|---------------------------------------------------------------|----------------------------------------------------------------|  
|envelope1: p1<br /><br /> envelope2: p3<br /><br /> document1: p2<br /><br /> document2: p4 和 p5<br /><br /> document3： 无升级<br /><br /> document4： 无升级|文档 1: p1、 p2<br /><br /> document2: p1、 p3、 p4，p5<br /><br /> document3: p1，p3<br /><br /> document4: p1|文档 1: p1、 p2、 p3<br /><br /> document2: p1、 p3、 p4，p5<br /><br /> document3: p1，p3<br /><br /> document4: p1，p3|  
  
## <a name="see-also"></a>请参阅  
 [XML 消息信封](../core/xml-message-envelopes.md)   
 [XML 消息的结构](../core/structure-of-an-xml-message.md)   
 [如何为信封创建架构](../core/how-to-create-schemas-for-envelopes.md)