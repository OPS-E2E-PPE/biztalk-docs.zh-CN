---
title: 备份 A4SWIFT 数据库 |Microsoft 文档
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
ms.openlocfilehash: 4102d459d5b579491f42747f1d3fe0dd3d381b71
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005854"
---
# <a name="backing-up-the-a4swift-database"></a>备份 A4SWIFT 数据库
你应定期备份数据库中您的 BizTalk Server 和 A4SWIFT 系统，从而降低灾难性故障的风险。 这些数据库包括在 BizTalk Server 源系统和 A4SWIFT 数据库。 除了降低风险，这还将使你能够清除 A4SWIFT 历史记录文件可以增长到很大的大小。  
  
 有关备份 BizTalk Server 源系统中的数据库的详细信息，请参阅 BizTalk Server 帮助中的"备份和还原 BizTalk Server 数据库"主题。 本主题介绍用于将 BizTalk 数据库备份的备份 BizTalk Server 作业。  
  
 有关将 A4SWIFT 数据库备份的信息，请参阅 BizTalk Server 帮助中的"如何为返回向上自定义数据库"主题。 本主题介绍如何修改备份 BizTalk Server 作业，以包括自定义的 A4SWIFT 数据库。