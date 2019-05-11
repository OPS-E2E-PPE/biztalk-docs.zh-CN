---
title: 第 2 步：配置负载测试控制器和代理的计算机 |Microsoft Docs
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
ms.openlocfilehash: dc03e3d0df88da463c9e1481f849564086645dcb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379435"
---
# <a name="step-2-configure-load-test-controller-and-agent-computers"></a>第 2 步：配置负载测试控制器和代理的计算机

## <a name="overview"></a>概述
Visual Studio 可以生成模拟最多 250 个虚拟用户的本地负载测试运行的负载。 若要模拟 250 多个虚拟用户和/或启动测试从远程计算机需要安装 Visual Studio 负载测试虚拟用户。  
  
 所有负载测试执行本指南中的都启动两台计算机：  
  
- 一台计算机运行负载测试控制器和负载测试代理。  
  
- 运行负载测试代理仅作为另一台计算机。  
  
  测试结果存储在 SQL Server 数据库中的远程负载测试结果存储库中。  
  
  有关使用测试控制器和测试代理在多台测试计算机间分发负载测试的详细信息，请参阅[分发负载测试跨多个测试使用测试控制器和测试代理计算机](https://msdn.microsoft.com/library/dd728093.aspx)。  
  
## <a name="install-and-configure-the-load-test-controller-and-load-test-agents"></a>安装和配置负载测试控制器和负载测试代理  
 若要安装和配置负载测试控制器和负载测试代理，请参阅[安装和配置测试代理](https://docs.microsoft.com/visualstudio/test/lab-management/install-configure-test-agents)。
