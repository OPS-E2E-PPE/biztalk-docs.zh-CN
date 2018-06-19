---
title: 步骤 2： 配置负载测试控制器和代理计算机 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e9d937ac-55d8-48fa-bba2-3efe151587b8
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75a659d533b68cf525bcd782a2dadce72a6ebb0b
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
ms.locfileid: "24014084"
---
# <a name="step-2-configure-load-test-controller-and-agent-computers"></a>步骤 2： 配置负载测试控制器和代理的计算机

## <a name="overview"></a>概述
Visual Studio 可以生成模拟最多 250 个虚拟用户在本地的负载测试运行的负载。 模拟虚拟用户数超过 250 名和/或启动测试从远程计算机需要 Visual Studio 负载测试虚拟用户。  
  
 从两台计算机的所有负载测试执行本指南中已都启动：  
  
-   为负载测试控制器和负载测试代理运行的一台计算机。  
  
-   为负载测试代理只运行的另一台计算机。  
  
 测试结果存储在远程负载测试结果储存库中的 SQL Server 数据库。  
  
 有关使用测试控制器和测试代理在多台测试计算机之间分发负载测试的详细信息，请参阅[分发负载测试跨多个测试使用测试控制器和测试代理计算机](https://msdn.microsoft.com/library/dd728093.aspx)。  
  
## <a name="install-and-configure-the-load-test-controller-and-load-test-agents"></a>安装和配置的负载测试控制器和负载测试代理  
 若要安装并配置负载测试控制器和负载测试代理，请参阅[安装和配置测试代理](https://docs.microsoft.com/visualstudio/test/lab-management/install-configure-test-agents)。
