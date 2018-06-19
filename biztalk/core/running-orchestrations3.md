---
title: 运行 Orchestrations3 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, running
- Receive shape [Orchestration Designer], starting orchestrations
- Start Orchestration shape [Orchestration Designer], starting orchestrations
- Call Orchestration shape [Orchestration Designer], starting orchestrations
- Receive shape [Orchestration Designer], activating orchestrations
ms.assetid: 5bfe61c9-80e0-4a0a-b6b1-ab48037e665e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 550fc1e03f3583215a817028917000c9a9c3074a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269045"
---
# <a name="running-orchestrations"></a>运行业务流程
业务流程实例旨在能够触发通过在另一个业务流程进行显式调用 — 使用**调用 Orchestration**形状或**启动 Orchestration**形状 — 或收到激活消息。 中指定的激活消息架构**消息**属性。 应相应地，设计您的业务流程和设置**激活**属性**接收**形状为 true，或者请确保调用 orchestration 存在并且正确配置为运行新的业务流程。  
  
 可以运行任何实例之前，你必须首先将绑定和部署 BizTalk 程序集，然后登记和启动要开始处理的业务流程引擎。 有关详细信息，请参阅[部署 BizTalk 中的程序集到 BizTalk 应用程序的 Visual Studio](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)和[部署和管理 BizTalk 应用程序](../core/deploying-and-managing-biztalk-applications.md)。 当一条消息呈现给与激活的条件相符的引擎或业务流程调用从另一个业务流程，接收，引擎创建业务流程的新实例并运行该实例。 它可以同时运行多个不同的实例。  
  
## <a name="calling-and-starting-orchestrations"></a>调用和启动业务流程  
 **调用 Orchestration**形状和**启动 Orchestration**形状可以用于激活另一个业务流程。 在这两种情况下，调用方可以传入参数，以交换信息与其他业务流程。 有关详细信息，请参阅[如何将参数添加到业务流程](../core/how-to-add-parameters-to-orchestrations.md)。  
  
## <a name="using-activation-receives-with-filter-expression"></a>使用激活接收使用筛选器表达式  
 **接收**形状还可能使用的筛选器表达式来要求以激活的进一步条件。 如果此消息是正确的类型，而且某些属性或消息属性满足所有筛选表达式中的条件**接收**形状接受消息并激活业务流程。 接收形状称为*激活接收*。  
  
## <a name="see-also"></a>另请参阅  
 [如何配置调用业务流程形状](../core/how-to-configure-the-call-orchestration-shape.md)   
 [如何配置开始业务流程形状](../core/how-to-configure-the-start-orchestration-shape.md)   
 [如何配置接收形状](../core/how-to-configure-the-receive-shape.md)   
 [生成并运行业务流程](../core/building-and-running-orchestrations.md)