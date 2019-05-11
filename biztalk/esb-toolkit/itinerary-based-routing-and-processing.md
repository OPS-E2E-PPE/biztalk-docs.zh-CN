---
title: 基于路线的路由和处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e8354538-e45c-487d-a380-59f497ea060f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6593a9ff2a90f9b906352ecad1bec70e4f601994
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65261541"
---
# <a name="itinerary-based-routing-and-processing"></a>基于路线的路由和处理
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]实现路由的名单模式通过自定义管道组件使用。 消息元数据和其他因素用于确定相应的传送名单，也称为路线，以便使用为每个消息。 此传送名单可以执行消息转换、 调用业务流程服务，并定义消息路由 BizTalk Server 将执行的步骤、 有效地分离核心 BizTalk Server 引擎中的消息处理指令。  
  
 路线的处理方式的详细信息，请参阅[主要方案和开发任务](../esb-toolkit/key-scenarios-and-development-tasks.md)。