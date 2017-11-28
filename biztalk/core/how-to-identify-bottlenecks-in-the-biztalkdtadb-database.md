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
# <a name="how-to-identify-bottlenecks-in-the-biztalkdtadb-database"></a><span data-ttu-id="5e811-102">如何找出 BizTalkDTADb 数据库的瓶颈</span><span class="sxs-lookup"><span data-stu-id="5e811-102">How to Identify Bottlenecks in the BizTalkDTADb Database</span></span>
<span data-ttu-id="5e811-103">若要找出 BizTalkDTADb 数据库的瓶颈，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="5e811-103">To identify bottlenecks in the BizTalkDTADb database, perform the following steps:</span></span>  
  
1.  <span data-ttu-id="5e811-104">确保 SQL 代理服务正在运行。</span><span class="sxs-lookup"><span data-stu-id="5e811-104">Ensure that the SQL-Agent Service is running.</span></span>  
  
2.  <span data-ttu-id="5e811-105">确保存档/清除作业正在运行并成功完成。</span><span class="sxs-lookup"><span data-stu-id="5e811-105">Ensure that the Archive/Purge Job is running and completing successfully.</span></span>  
  
3.  <span data-ttu-id="5e811-106">验证有足够的磁盘空间可用于 DTADb 存档和数据库增长。</span><span class="sxs-lookup"><span data-stu-id="5e811-106">Verify that sufficient free disk space is available for the DTADb archives and database growth.</span></span>