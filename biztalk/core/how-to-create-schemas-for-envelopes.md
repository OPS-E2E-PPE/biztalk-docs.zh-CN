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
ms.openlocfilehash: 4c3da9c438de2f6fb6140e33f986631c5bf3e12b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989638"
---
# <a name="create-schemas-for-envelopes"></a>为信封创建架构

## <a name="overview"></a>概述
创建 XML 消息架构中所述后[的 XML 消息创建架构](../core/how-to-create-schemas-for-xml-messages.md)，将**信封**属性**架构**节点到**是**. 根据信封架构的某些特性（例如是否具有多个根节点），您将需要设置其他一些特定于信封的属性。 有关详细信息，请参阅[信封架构](../core/envelope-schemas.md)。  

 信封的正文 XPath 属性指向包含文档元素的元素。 XPath 实际指向的元素不属于该文档。  

## <a name="see-also"></a>请参阅  
- [管理项目中的架构](../core/managing-schemas-within-projects.md)
- **信封**属性 [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
