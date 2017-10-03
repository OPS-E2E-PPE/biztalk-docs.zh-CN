---
title: "如何确定 BAM 数据库中的瓶颈 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6814c0df-3ce1-44f8-8e63-af6e23336c6d
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8fa54379d6d314993ac33b7d6395f061e48849d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-identify-bottlenecks-in-the-bam-database"></a><span data-ttu-id="5c64d-102">如何确定 BAM 数据库中的瓶颈</span><span class="sxs-lookup"><span data-stu-id="5c64d-102">How to Identify Bottlenecks in the BAM Database</span></span>
<span data-ttu-id="5c64d-103">若要找出 BAM 数据库的瓶颈，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="5c64d-103">To identify bottlenecks in the BAM database, perform the following steps:</span></span>  
  
1.  <span data-ttu-id="5c64d-104">确保活动实例数不再增加。</span><span class="sxs-lookup"><span data-stu-id="5c64d-104">Ensure that the Active Instances count is not climbing.</span></span>  
  
2.  <span data-ttu-id="5c64d-105">确保 SQL 代理服务正在运行。</span><span class="sxs-lookup"><span data-stu-id="5c64d-105">Ensure that the SQL-Agent Service is running.</span></span>  
  
3.  <span data-ttu-id="5c64d-106">如果配置了 OLAP 分析，请确保 BAM_AN_ job 按周期性间隔运行。</span><span class="sxs-lookup"><span data-stu-id="5c64d-106">If OLAP Analysis is configured ensure that the BAM_AN_ job is running at periodic intervals.</span></span>  
  
4.  <span data-ttu-id="5c64d-107">确保 BAM_DM_(Data Maintenance) 作业被安排为按周期性间隔运行。</span><span class="sxs-lookup"><span data-stu-id="5c64d-107">Ensure that BAM_DM_ (Data Maintenance) job is scheduled to run at periodic intervals.</span></span>