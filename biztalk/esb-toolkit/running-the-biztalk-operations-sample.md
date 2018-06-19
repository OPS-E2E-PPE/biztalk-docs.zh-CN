---
title: 运行 BizTalk 操作示例 |Microsoft 文档
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
ms.openlocfilehash: 57480e6020b2ab262d7d9db522b9dd2f79aa49cf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294533"
---
# <a name="running-the-biztalk-operations-sample"></a>运行 BizTalk 操作示例
Microsoft BizTalk Operations 示例使用 Windows 窗体测试客户端应用程序来执行 BizTalk 操作 Web 服务方法并显示结果。 你可以打开测试客户端项目，以便运行它，并检查代码以了解如何使用你自己的面向服务的体系结构 (SOA) 和 ESB 应用程序中的 BizTalk 操作 Web 服务。  
  
 在 Windows 资源管理器，打开名为 \Samples\BizTalkOperations\bin\Debug 的文件夹，然后执行应用程序 Microsoft.Practices.ESB.BizTalkOperations.Test.Client.exe。  
  
 图 1 显示 BizTalk 操作 Web 服务测试客户端应用程序。 你可以执行 BizTalk 操作 Web 服务使用此应用程序的所有的函数。 应用程序中的树视图格式显示结果，并显示服务返回的消息。  
  
 ![Web 服务测试](../esb-toolkit/media/ch6-webservicetest.gif "Ch6 WebServiceTest")  
  
 **图 1**  
  
 **BizTalk 操作 Web 服务测试客户端**  
  
 若要执行不需要任何参数 BizTalk Operations Web 服务的方法，只需单击应用程序窗口的左侧相应的按钮。 有关是否需要输入的参数的方法在窗口顶部的下拉列表中选择的方法，输入参数值，你需要，，然后单击**调用服务**按钮。  
  
## <a name="how-the-sample-works"></a>此示例的工作原理  
 示例应用程序实例化 ESB BizTalk 操作 Web 服务，并调用相应的方法具体取决于所选应用程序中的设置。 通过你在中输入应用程序的控制作为参数指向所选的服务方法中，将值和它收集从服务方法，以在应用程序窗口中显示输出。