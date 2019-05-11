---
title: 嵌套位置和分隔记录 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d1688f04-d3c7-492c-82f7-a734bec0e409
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf45d62d65f0d24dc711978e3e7d50c141330213
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65263503"
---
# <a name="nested-positional-and-delimited-records"></a>嵌套位置和分隔记录
在受 Microsoft 的平面文件格式[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、 位置和分隔记录的某些组合允许和不允许其他人。 允许使用以下组合：  
  
- 中的分隔符用于确定所有记录，及其从属记录之间的边界和中使用的 （可能有所不同） 分隔符来分隔这些记录中的字段的平面文件。  
  
- 平面文件在其中确定所有记录，其从属记录及其字段之间的边界基于它们的位置根据预定义的记录和字段长度文件中。  
  
- 平面的文件中的分隔符用于确定至少之间的边界的最外面的一组记录在文件中，并在其中使用分隔和位置从属记录的组合。 分别使用分隔符或固定的字段长度确定分隔或位置从属记录中字段之间的边界。 位置 （从属） 记录的从属记录必须也是位置;换而言之，一旦该文件的一部分从分隔为位置记录切换，文件的整个从属部分必须是位置。  
  
  由于将导致解析多义性，位置记录，只要出现，都不得包含分隔从属记录。  
  
## <a name="see-also"></a>请参阅  
 [创建平面文件消息架构时的注意事项](../core/considerations-when-creating-flat-file-message-schemas.md)