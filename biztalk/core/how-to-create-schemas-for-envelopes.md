---
title: 如何为包络线创建架构 |Microsoft 文档
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
ms.openlocfilehash: 7308a093f9f95ce2342f268554deb67193aea053
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249589"
---
# <a name="create-schemas-for-envelopes"></a>为包络线创建架构

## <a name="overview"></a>概述
创建 XML 消息架构中所述之后[创建架构的 XML 消息](../core/how-to-create-schemas-for-xml-messages.md)，将其设置**信封**属性**架构**节点**是**. 根据信封架构的某些特性（例如是否具有多个根节点），您将需要设置其他一些特定于信封的属性。 有关详细信息，请参阅[信封架构](../core/envelope-schemas.md)。  
  
 信封的正文 XPath 属性指向包含文档元素的元素。 XPath 实际指向的元素不属于该文档。  
  
## <a name="see-also"></a>另请参阅  
-  [管理架构在项目中](../core/managing-schemas-within-projects.md)
-  **信封**属性[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]