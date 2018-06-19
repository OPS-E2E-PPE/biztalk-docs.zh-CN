---
title: 运行多个 Web 服务示例 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b201c7c3-213a-4009-8872-5a4c1cbb8195
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4ec54fabb7ed140fd88b5a2d5a07d788805c741e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294797"
---
# <a name="running-the-multiple-web-services-sample"></a>运行多个 Web 服务示例
多个 Web 服务示例使用 Windows 窗体测试客户端应用程序的入口路线示例。  
  
 **若要运行多个 Web 服务示例**  
  
1.  如果 GlobalBank.ESB 应用程序尚未运行，使用 Microsoft BizTalk 管理控制台来启动它。  
  
2.  在 Windows 资源管理器，打开文件夹 \Source\Samples\Itinerary\Source\ESB。你的安装位置的 Itinerary.Test[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]示例，，然后启动指定 Esb.Itinerary.Test.exe 的应用程序。  
  
3.  清除**使用 WCF 服务**复选框，以便可以利用客户端路线。  
  
4.  单击**负载路线**按钮，，然后选择一个位于 \Source\Samples\MultipleWebServices\Itineraries 文件夹示例路线。  
  
5.  选择**两个方式服务**复选框，这样应用程序将执行双向路线服务操作。  
  
6.  单击**LoadMessage**按钮，然后从 \Source\Samples\Itinerary\Test\Data 文件夹然后选择 NAOrderDoc.xml 示例消息。  
  
7.  单击**SubmitRequest**按钮以将请求发送到路线提升服务。 等待响应消息显示在**结果**框。  
  
 有关如何在多个 Web 服务示例使用 ESB 路线服务的信息，请参阅[多个 Web 服务示例的工作原理](../esb-toolkit/how-the-multiple-web-services-sample-works.md)。