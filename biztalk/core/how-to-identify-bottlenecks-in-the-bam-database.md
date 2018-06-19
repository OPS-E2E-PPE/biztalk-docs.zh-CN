---
title: 如何确定 BAM 数据库中的瓶颈 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6814c0df-3ce1-44f8-8e63-af6e23336c6d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8fa54379d6d314993ac33b7d6395f061e48849d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254101"
---
# <a name="how-to-identify-bottlenecks-in-the-bam-database"></a>如何确定 BAM 数据库中的瓶颈
若要找出 BAM 数据库的瓶颈，请执行以下步骤：  
  
1.  确保活动实例数不再增加。  
  
2.  确保 SQL 代理服务正在运行。  
  
3.  如果配置了 OLAP 分析，请确保 BAM_AN_ job 按周期性间隔运行。  
  
4.  确保 BAM_DM_(Data Maintenance) 作业被安排为按周期性间隔运行。