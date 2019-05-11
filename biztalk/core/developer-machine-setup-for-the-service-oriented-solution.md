---
title: 面向开发人员计算机设置为服务的解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- developer servers
- service solution tutorial, deployment prerequisites
- service solution tutorial, developer servers
ms.assetid: a088696f-c1ee-4578-ac02-af29b6de086b
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7a296118d9154d51ffc1dba22524a50cc7e76b6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351593"
---
# <a name="developer-machine-setup-for-the-service-oriented-solution"></a>面向开发人员计算机设置为服务的解决方案
面向服务的体系结构 (SOA) 是用于构建分布式的系统的方法。 面向服务的解决方案演示了几种使用不同的协议的后端系统可以整合到单个服务的客户端可以使用。 此解决方案将服务集成与可确保为需要满足的服务级别协议的送达和性能特征的方法。  
  
 面向的解决方案只现代性的在 BizTalk Server 和业务线 (LOB) 应用程序服务器连接到它的服务级别协议方案的服务提供三秒使用的服务请求进行响应。 这三个秒之一可能由 BizTalk Server 会占用。  
  
 有三个版本的面向服务的解决方案： 适配器、 内联和存根 （stub）。 有关面向服务的解决方案的三个版本之间的差异的详细信息，请参阅[了解面向服务的解决方案](../core/understanding-the-service-oriented-solution.md)。 作为开发人员，你可以使用该方案的存根版本运行的方案。 若要运行，此版本不需要任何 LOB 后端服务器。 完成此操作后可以使用方案的适配器版本，若要了解如何对各种适配器和后端服务器可以集成并配置为响应作为单个服务中使用的 BizTalk 服务器。 然后可以度量 BizTalk Server 和及其适配器引起的延迟时间。  
  
 如果 BizTalk server 的延迟超过其服务需求，您可以通过安装和运行 SOA 内联版本来绕过 LOB 适配器持久化点。 此版本将忽略适配器以及随后由于 MessageBox 持久化点延迟贡献。 相反，内联版本通过 DCOM 等远程过程调用 (RPC) 机制了直接转到后端服务器。  
  
 有关 MessageBox 持久化点的详细信息，请参阅[持久化和业务流程引擎](../core/persistence-and-the-orchestration-engine.md)。  
  
 本部署指南介绍如何安装和测试面向服务的解决方案在单台计算机上的三个版本。  
  
 有关面向服务的解决方案的详细信息，请参阅[了解面向服务的解决方案](../core/understanding-the-service-oriented-solution.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [在安装面向服务的解决方案之前](../core/before-installing-the-service-oriented-solution.md)  
  
-   [如何安装该服务的存根版本面向解决方案](../core/how-to-install-the-stub-version-of-the-service-oriented-solution.md)  
  
-   [如何安装的内联版本和适配器版本的服务面向解决方案](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md)  
  
-   [如何运行该服务面向解决方案](../core/how-to-run-the-service-oriented-solution.md)