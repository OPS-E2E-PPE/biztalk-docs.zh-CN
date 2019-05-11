---
title: 如何为信封创建架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ae1c991c-447f-497e-803c-1cb8cad2846b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 255236d6a28ee82fa4131b2189a97c9d0962c7d3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338997"
---
# <a name="create-schemas-for-envelopes"></a>为信封创建架构

## <a name="overview"></a>概述
创建 XML 消息架构中所述后[的 XML 消息创建架构](../core/how-to-create-schemas-for-xml-messages.md)，将**信封**属性**架构**节点到**是**. 具体取决于某些特征的信封架构，如是否有多个根节点，你将需要设置多个其他特定于信封的属性。 有关详细信息，请参阅[信封架构](../core/envelope-schemas.md)。  

 正文信封的 XPath 属性指向包含文档元素的元素。 XPath 指向的实际元素不属于该文档。  

## <a name="see-also"></a>请参阅  
- [管理项目中的架构](../core/managing-schemas-within-projects.md)
- **信封**属性 [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
