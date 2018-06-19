---
title: 方案： 部署两个版本的应用程序 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, multiple assemblies
- assemblies, multiple assemblies
- receive locations, examples
- assemblies, deploying
- assemblies, examples
ms.assetid: 3e79a7df-bf77-4a0b-86ec-359fcf3489b3
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f1bb4f04e8b00dd171de89bbed6f01d2a2d1e2e2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268933"
---
# <a name="scenario-deploying-two-versions-of-an-application"></a>方案： 部署两个版本的应用程序
本主题介绍在 BizTalk 组中部署某应用程序的两个版本的方案，以便它们可以同时运行。 在本方案中，您需要部署该应用程序的主要新版本。 这要求合作伙伴改变他们与系统的交互，这是因为架构或协议发生了变化 – 变化主要来自新的应用程序。 此系统的转变已经过测试，但不是在全面的生产系统规模下测试的。 您希望最初在 20% 的合作伙伴的范围内试用新系统，而后逐渐将试用百分比扩大到所有合作伙伴。  
  
 由于这两个应用程序在两个不同的接收位置接收消息，您必须指示那些应该使用新版应用程序的合作伙伴将消息发送到新的 URL，以便通过新版本来处理这些消息。  
  
 下图显示了典型的并行应用程序部署方案。  
  
 ![部署在一起的两个程序集版本](../core/media/sidebysideassemblyversions.gif "SideBySideAssemblyVersions")  
  
## <a name="see-also"></a>另请参阅  
 [应用程序部署和管理方案](../core/application-deployment-and-management-scenarios.md)