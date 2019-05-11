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
# <a name="how-to-identify-bottlenecks-in-the-bam-database"></a><span data-ttu-id="b56dd-102">如何找出 BAM 数据库的瓶颈</span><span class="sxs-lookup"><span data-stu-id="b56dd-102">How to Identify Bottlenecks in the BAM Database</span></span>
<span data-ttu-id="b56dd-103">若要找出 BAM 数据库的瓶颈，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="b56dd-103">To identify bottlenecks in the BAM database, perform the following steps:</span></span>  
  
1.  <span data-ttu-id="b56dd-104">确保活动实例数不再增加。</span><span class="sxs-lookup"><span data-stu-id="b56dd-104">Ensure that the Active Instances count is not climbing.</span></span>  
  
2.  <span data-ttu-id="b56dd-105">确保 SQL 代理服务正在运行。</span><span class="sxs-lookup"><span data-stu-id="b56dd-105">Ensure that the SQL-Agent Service is running.</span></span>  
  
3.  <span data-ttu-id="b56dd-106">如果配置了 OLAP 分析，请确保 BAM_AN_ job 按周期性间隔运行。</span><span class="sxs-lookup"><span data-stu-id="b56dd-106">If OLAP Analysis is configured ensure that the BAM_AN_ job is running at periodic intervals.</span></span>  
  
4.  <span data-ttu-id="b56dd-107">确保 BAM_DM_(Data Maintenance) 作业被安排为按周期性间隔运行。</span><span class="sxs-lookup"><span data-stu-id="b56dd-107">Ensure that BAM_DM_ (Data Maintenance) job is scheduled to run at periodic intervals.</span></span>