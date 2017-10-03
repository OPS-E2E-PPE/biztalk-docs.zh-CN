---
title: "步骤 2： 配置负载测试控制器和代理计算机 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e9d937ac-55d8-48fa-bba2-3efe151587b8
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f931a05796856816e19b53ff5cba9f53b48c3e2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-configure-load-test-controller-and-agent-computers"></a>步骤 2： 配置负载测试控制器和代理的计算机
Visual Studio 2010 旗舰版版可生成模拟最多 250 个虚拟用户在本地的负载测试运行的负载。 模拟虚拟用户数超过 250 名和/或启动测试从远程计算机需要 Visual Studio 负载测试虚拟用户包 2010年。  
  
 从两台计算机的所有负载测试执行本指南中已都启动：  
  
-   为负载测试控制器和负载测试代理运行的一台计算机。  
  
-   为负载测试代理只运行的另一台计算机。  
  
 测试结果存储在远程负载测试结果储存库中的 SQL Server 2008 R2 数据库。  
  
 有关使用测试控制器和测试代理在多台测试计算机之间分发负载测试的详细信息，请参阅[分发负载测试跨多个测试使用测试控制器和测试代理计算机](http://go.microsoft.com/fwlink/?LinkId=208406)(http://go.microsoft.com/fwlink/？LinkId = 208406)。  
  
## <a name="install-and-configure-the-load-test-controller-and-load-test-agents"></a>安装和配置的负载测试控制器和负载测试代理  
 若要安装并配置负载测试控制器和负载测试代理，请参阅主题中的以下部分[安装和配置 Visual Studio Agents 和测试和生成控制器](http://go.microsoft.com/fwlink/?LinkId=208455)(http://go.microsoft.com/fwlink/?LinkId=208455):  
  
-   要设置测试控制器，请按照中的过程[安装测试控制器](http://go.microsoft.com/fwlink/?LinkId=208454)(http://go.microsoft.com/fwlink/?LinkId=208454) 部分。  
  
-   要设置测试代理，请按照中的过程[安装测试代理](http://go.microsoft.com/fwlink/?LinkId=208456)(http://go.microsoft.com/fwlink/?LinkId=208456) 部分。