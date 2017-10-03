---
title: "备份 A4SWIFT 数据库 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- backing up A4SWIFT database
- A4SWIFT database, backing up
ms.assetid: 53e46380-5be7-4d4c-b04c-d917ab40c07c
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4cd2cd1eadf3dc6f11a6e3178258caaaf88006d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="backing-up-the-a4swift-database"></a>备份 A4SWIFT 数据库
你应定期备份数据库中您的 BizTalk Server 和 A4SWIFT 系统，从而降低灾难性故障的风险。 这些数据库包括在 BizTalk Server 源系统和 A4SWIFT 数据库。 除了降低风险，这还将使你能够清除 A4SWIFT 历史记录文件可以增长到很大的大小。  
  
 有关你的 BizTalk Server 源系统中的数据库备份的详细信息，请参阅中的"备份和还原 BizTalk Server 数据库"主题[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]帮助。 本主题介绍用于将 BizTalk 数据库备份的备份 BizTalk Server 作业。  
  
 有关备份 A4SWIFT 数据库的信息，请参阅中的"如何为返回向上自定义数据库"主题[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]帮助。 本主题介绍如何修改备份 BizTalk Server 作业，以包括自定义的 A4SWIFT 数据库。