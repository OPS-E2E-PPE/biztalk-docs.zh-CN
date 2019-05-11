---
title: 运行 BizTalk 操作示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e91d4e57-ba94-4730-8c5a-4c96902f313f
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 681a7a2d99c7488c94d3b824fa3e7d707db435ac
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292536"
---
# <a name="running-the-biztalk-operations-sample"></a>运行 BizTalk 操作示例
Microsoft BizTalk 操作示例使用 Windows 窗体测试客户端应用程序来执行 BizTalk 操作 Web 服务的方法，并显示结果。 您可以打开测试客户端项目以运行它并检查代码，请参阅如何使用你自己的面向服务的体系结构 (SOA) 和 ESB 应用程序中的 BizTalk 操作 Web 服务。  
  
 在 Windows 资源管理器，打开名为 \Samples\BizTalkOperations\bin\Debug，文件夹，然后执行应用程序 Microsoft.Practices.ESB.BizTalkOperations.Test.Client.exe。  
  
 图 1 显示了 BizTalk 操作 Web 服务的测试客户端应用程序。 您可以执行使用此应用程序的 BizTalk 操作 Web 服务的所有函数。 应用程序中的树视图格式显示结果，并显示服务返回的消息。  
  
 ![Web 服务测试](../esb-toolkit/media/ch6-webservicetest.gif "Ch6-WebServiceTest")  
  
 **图 1**  
  
 **BizTalk 操作 Web 服务测试客户端**  
  
 若要执行不需要任何参数的 BizTalk 操作 Web 服务方法，只需单击左侧和右侧的应用程序窗口中的相应按钮。 对于需要输入的参数的方法在窗口顶部的下拉列表中选择的方法，输入参数值要求，然后依次**调用服务**按钮。  
  
## <a name="how-the-sample-works"></a>示例工作原理  
 示例应用程序实例化 ESB BizTalk 操作 Web 服务，并调用相应的方法，具体取决于应用程序中选择的设置。 它将传递的值中输入应用程序控制作为参数给选定的服务方法，并从服务方法在应用程序窗口中显示收集输出。