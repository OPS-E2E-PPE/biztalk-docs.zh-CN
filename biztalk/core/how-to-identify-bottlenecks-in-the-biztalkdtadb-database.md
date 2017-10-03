---
title: "如何确定 BizTalkDTADb 数据库中的瓶颈 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d4499bc3-d50b-4b97-b19c-93c7bcc40483
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c7463a0288733936189d3cbbb69b59b3b202419
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-identify-bottlenecks-in-the-biztalkdtadb-database"></a>如何找出 BizTalkDTADb 数据库的瓶颈
若要找出 BizTalkDTADb 数据库的瓶颈，请执行以下步骤：  
  
1.  确保 SQL 代理服务正在运行。  
  
2.  确保存档/清除作业正在运行并成功完成。  
  
3.  验证有足够的磁盘空间可用于 DTADb 存档和数据库增长。