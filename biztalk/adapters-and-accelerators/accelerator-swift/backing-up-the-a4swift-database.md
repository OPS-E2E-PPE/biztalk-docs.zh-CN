---
title: 备份 A4SWIFT 数据库 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- backing up A4SWIFT database
- A4SWIFT database, backing up
ms.assetid: 53e46380-5be7-4d4c-b04c-d917ab40c07c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89e69325509131c6ea1674c3f6c3b6153f3ea2f7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378655"
---
# <a name="backing-up-the-a4swift-database"></a>备份 A4SWIFT 数据库
你应定期将数据库备份 BizTalk Server 和 A4SWIFT 系统到较低的灾难性故障的风险中。 这些数据库包括在 BizTalk Server 源系统和 A4SWIFT 数据库。 除了降低风险，这也将启用你清除 A4SWIFT 历史记录文件可以增长到很大的大小。  
  
 有关 BizTalk Server 源系统中的数据库备份的详细信息，请参阅 BizTalk Server 帮助中的"备份和还原 BizTalk Server 数据库"主题。 本主题介绍用于将备份 BizTalk 数据库的备份 BizTalk Server 作业。  
  
 有关备份 A4SWIFT 数据库的信息，请参阅 BizTalk Server 帮助中的"如何为返回了自定义数据库"主题。 本主题介绍如何修改备份 BizTalk Server 作业，包括自定义的 A4SWIFT 数据库。