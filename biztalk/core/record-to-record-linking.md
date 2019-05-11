---
title: 记录到记录的链接 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9a3fa4d7-5689-4f55-af1b-369defa37037
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91108b194a186488867ff083c0129570b5fd9477
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398036"
---
# <a name="record-to-record-linking"></a>记录到记录链接

## <a name="overview"></a>概述
在 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，可以使用 BizTalk 映射器创建多个同时在源和目标架构的相似部分之间的链接。 在以前版本的 BizTalk Server，您必须分别创建此类链接一次一个。 有两种不同类型的记录到记录的链接，在源和目标架构链接的记录，按如下所示的结构的相似性的程度上基于每个适用于不同方案：  
  
-   **结构链接。** 使用结构链接时在源和目标架构中所链接的记录结构是相同或非常相似。  
  
-   **名称匹配链接。** 使用名称匹配链接时仍类似，在源和目标架构中链接的记录的结构和匹配的记录和字段名称，但结构性异常多于结构链接具有可处理量。  
  
    > [!NOTE]
    >  记录到记录的链接适用于链接仅在使用配置的值复制**源链接**属性。  
  
## <a name="record-to-record-linking-structure-links"></a>记录到记录链接：结构链接  
 使用结构链接时要在源和目标架构中链接的记录的结构不相同或几乎完全相同。  
  
 如果您的架构的结构完全相同，只需每个架构的根节点处添加一个链接。 在快捷菜单中，选择所需的链接模式。  
  
 如果您的架构中特定记录的结构完全相同，只需添加这些记录中每个架构之间的一个链接。 在快捷菜单中，选择所需的链接模式。  
  
 有关如何配置记录到记录的信息链接作为使用结构链接或名称匹配链接，请参阅[自动链接记录](../core/how-to-link-records-automatically.md)。  
  
> [!NOTE]
>  结构链接是记录到记录的链接的默认类型。  
  
## <a name="record-to-record-linking-name-matching-links"></a>记录到记录链接：名称匹配链接  
 使用名称匹配链接时要在源和目标架构中链接的记录结构非常相似，但又不完全相同。 例如，源或目标架构可能有多个从属记录或要比其他架构中链接的节点中的字段。  
  
 若要创建具有近似匹配结构，包括整个架构，如果适用，在源和目标架构的部分之间的名称匹配链接创建链接来自子层次结构父节点和在另一台结束子层次结构父节点。 在快捷菜单中，选择所需的模式。 链接这些节点后，链接会自动创建的所有从属记录和已命名相同，并且具有相同子结构的源和目标架构中的字段。  
  
 有关如何配置记录到记录的信息链接作为使用结构链接或名称匹配链接，请参阅[自动链接记录](../core/how-to-link-records-automatically.md)。  
  
## <a name="see-also"></a>请参阅  
 [自动链接记录](../core/how-to-link-records-automatically.md)   
 [编辑链接属性](../core/how-to-edit-link-properties.md)