---
title: 测试 JMS MQRFH2 示例安装 |Microsoft 文档
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
ms.openlocfilehash: 5970f12479cddfb6a635cbd00dd139495a2f6242
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294613"
---
# <a name="test-the-jms-mqrfh2-sample-installation"></a>测试 JMS MQRFH2 示例安装
你可以检查成功地安装和操作的[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]JMS MQRFH2 示例之前执行任何示例方案。  
  
 **若要测试 JMS MQRFH2 示例安装**  
  
1.  使用"RFHUtil"JMS 测试实用程序 \Source\Samples\JMS\Test\Data\Load 文件夹中的测试消息写入名为 ESB 的队列。JMS。示例。SENDTOBIZTALK。  
  
2.  此示例将消息发送到目标队列和到答复队列消息的副本。