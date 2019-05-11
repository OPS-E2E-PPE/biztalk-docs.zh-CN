---
title: 如何找出 BAM 数据库的瓶颈 |Microsoft Docs
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
ms.openlocfilehash: 9fe47056d70e1b7e0f93bf9ba2451ade489a5c93
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337254"
---
# <a name="how-to-identify-bottlenecks-in-the-bam-database"></a>如何找出 BAM 数据库的瓶颈
若要找出 BAM 数据库的瓶颈，请执行以下步骤：  
  
1.  确保活动实例数不再增加。  
  
2.  确保 SQL 代理服务正在运行。  
  
3.  如果配置了 OLAP 分析，请确保 BAM_AN_ job 按周期性间隔运行。  
  
4.  确保 BAM_DM_(Data Maintenance) 作业被安排为按周期性间隔运行。