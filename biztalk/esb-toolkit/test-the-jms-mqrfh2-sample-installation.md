---
title: 测试 JMS MQRFH2 示例安装 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 965e985d-f0fe-4b0f-b01b-cf98d1e2f6a4
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d22f609ef8de65845ff36cc1e60b2942faa956de
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65268668"
---
# <a name="test-the-jms-mqrfh2-sample-installation"></a>测试 JMS MQRFH2 示例安装
你可以检查成功安装和操作的[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]JMS MQRFH2 示例之前执行任何示例方案。  
  
 **若要测试 JMS MQRFH2 示例安装**  
  
1.  使用"RFHUtil"JMS 测试实用程序将 \Source\Samples\JMS\Test\Data\Load 文件夹中的测试消息写入名为 ESB 的队列。JMS。示例。SENDTOBIZTALK。  
  
2.  该示例将消息发送到目标队列和到答复队列消息的副本。