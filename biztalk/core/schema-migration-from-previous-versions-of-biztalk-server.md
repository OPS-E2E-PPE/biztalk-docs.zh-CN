---
title: 从以前版本的 BizTalk Server 迁移架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bdc86401-2002-40b8-a919-2c00cf42b557
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3aabd12fa240688d58cf4c841f0647f2db24df8f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396946"
---
# <a name="schema-migration-from-previous-versions-of-biztalk-server"></a>从早期版本的 BizTalk Server 迁移架构
此版本的 BizTalk Server 使用 XML 架构定义 (XSD) 语言来表示消息架构，而以前的版本使用的 XML 数据缩减 (XDR) 语法来表示消息架构。 如果要从早期版本的 BizTalk Server 进行迁移，必须将转换为使用 XSD 而不是 XDR 架构。  
  
 需要执行以下任务以将 BizTalk 架构从 XDR 语法转换为 XSD 语法：  
  
- 更改架构文件为 to.xsd 的扩展。  
  
- 将重命名的架构添加到相应的 BizTalk 项目。  
  
- 通过在 BizTalk 编辑器中打开该架构，可将重命名的架构 XDR 转换为 XSD。  
  
- 使其永久转换保存该架构。  
  
  有关如何执行这些步骤的详细信息，请参阅[如何将 XDR 架构迁移到 XSD 架构](../core/how-to-migrate-xdr-schemas-to-xsd-schemas.md)。  
  
## <a name="see-also"></a>请参阅  
 [有关架构](../core/about-schemas.md)   
 [如何将 XDR 架构迁移到 XSD 架构](../core/how-to-migrate-xdr-schemas-to-xsd-schemas.md)   
 [迁移平面文件记录](../core/migrating-flat-file-records.md)