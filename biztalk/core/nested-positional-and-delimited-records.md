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
ms.openlocfilehash: 3896eb41a52ee356021a6fcf7e7621267f8764f8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971214"
---
# <a name="nested-positional-and-delimited-records"></a>嵌套位置和分隔记录
在受 Microsoft 的平面文件格式[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、 位置和分隔记录的某些组合允许和不允许其他人。 允许使用以下组合：  
  
- 平面文件中的分隔符用于确定所有记录及其从属记录之间的边界，平面文件中（可能有所不同）的分隔符用于在这些记录中分隔字段。  
  
- 平面文件中所有记录、其从属记录及其字段之间的边界基于它们在文件中的位置根据预定义记录和字段长度来确定。  
  
- 平面文件中的分隔符用于确定文件中至少最外层一组记录之间的边界，平面文件中使用分隔和位置从属记录的组合。 分别使用分隔符或固定字段长度来确定分隔或位置从属记录中字段之间的边界。 位置（从属）记录的从属记录必须也是位置记录；换句话说，文件的某一部分从分隔记录切换为位置记录后，该文件的整个从属部分必须是位置记录。  
  
  由于将导致解析多义性，因此只要出现位置记录，都禁止位置记录包含分隔从属记录。  
  
## <a name="see-also"></a>请参阅  
 [创建平面文件消息架构时的注意事项](../core/considerations-when-creating-flat-file-message-schemas.md)