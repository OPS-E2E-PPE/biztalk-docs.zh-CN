---
title: 运行多个 Web 服务示例 |Microsoft Docs
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
ms.openlocfilehash: 52915c751f8857f26195c7df033dcf2327989760
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242726"
---
# <a name="running-the-multiple-web-services-sample"></a>运行多个 Web 服务示例
多个 Web 服务示例使用 Windows 窗体测试客户端应用程序的路线接入点示例。  
  
 **若要运行多个 Web 服务示例**  
  
1. 如果尚未运行 GlobalBank.ESB 应用程序，使用 Microsoft BizTalk 管理控制台来启动它。  
  
2. 在 Windows 资源管理器中打开文件夹 \Source\Samples\Itinerary\Source\ESB。安装位置的 Itinerary.Test[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]示例，并启动名为 Esb.Itinerary.Test.exe 应用程序。  
  
3. 清除**使用 WCF 服务**复选框，以便可以利用客户端的路线。  
  
4. 单击**负载路线**按钮，并选择其中一个示例路线 \Source\Samples\MultipleWebServices\Itineraries 文件夹中。  
  
5. 选择**两种方式服务**复选框，以便应用程序将执行双向路线服务操作。  
  
6. 单击**LoadMessage**按钮，并从 \Source\Samples\Itinerary\Test\Data 文件夹选择 NAOrderDoc.xml 示例消息。  
  
7. 单击**SubmitRequest**按钮以将请求发送到路线接入点服务。 等待响应消息中出现**结果**框。  
  
   有关多个 Web 服务示例如何使用 ESB 路线服务的信息，请参阅[多个 Web 服务示例工作原理](../esb-toolkit/how-the-multiple-web-services-sample-works.md)。