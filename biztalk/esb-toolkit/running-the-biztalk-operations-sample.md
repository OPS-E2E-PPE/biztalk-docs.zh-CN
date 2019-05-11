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
# <a name="running-the-biztalk-operations-sample"></a><span data-ttu-id="ed42a-102">运行 BizTalk 操作示例</span><span class="sxs-lookup"><span data-stu-id="ed42a-102">Running the BizTalk Operations Sample</span></span>
<span data-ttu-id="ed42a-103">Microsoft BizTalk 操作示例使用 Windows 窗体测试客户端应用程序来执行 BizTalk 操作 Web 服务的方法，并显示结果。</span><span class="sxs-lookup"><span data-stu-id="ed42a-103">The Microsoft BizTalk Operations sample uses a Windows Forms test client application to execute methods of the BizTalk Operations Web service and display the results.</span></span> <span data-ttu-id="ed42a-104">您可以打开测试客户端项目以运行它并检查代码，请参阅如何使用你自己的面向服务的体系结构 (SOA) 和 ESB 应用程序中的 BizTalk 操作 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="ed42a-104">You can open the test client project to run it and to examine the code to see how you can use the BizTalk Operations Web service in your own service-oriented architecture (SOA) and ESB applications.</span></span>  
  
 <span data-ttu-id="ed42a-105">在 Windows 资源管理器，打开名为 \Samples\BizTalkOperations\bin\Debug，文件夹，然后执行应用程序 Microsoft.Practices.ESB.BizTalkOperations.Test.Client.exe。</span><span class="sxs-lookup"><span data-stu-id="ed42a-105">In Windows Explorer, open the folder named \Samples\BizTalkOperations\bin\Debug, and then execute the application Microsoft.Practices.ESB.BizTalkOperations.Test.Client.exe.</span></span>  
  
 <span data-ttu-id="ed42a-106">图 1 显示了 BizTalk 操作 Web 服务的测试客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="ed42a-106">Figure 1 shows the test client application for the BizTalk Operations Web service.</span></span> <span data-ttu-id="ed42a-107">您可以执行使用此应用程序的 BizTalk 操作 Web 服务的所有函数。</span><span class="sxs-lookup"><span data-stu-id="ed42a-107">You can execute all the functions of the BizTalk Operations Web service using this application.</span></span> <span data-ttu-id="ed42a-108">应用程序中的树视图格式显示结果，并显示服务返回的消息。</span><span class="sxs-lookup"><span data-stu-id="ed42a-108">The application displays the results in a tree-view format and shows the message returned by the service.</span></span>  
  
 <span data-ttu-id="ed42a-109">![Web 服务测试](../esb-toolkit/media/ch6-webservicetest.gif "Ch6-WebServiceTest")</span><span class="sxs-lookup"><span data-stu-id="ed42a-109">![Web Service Test](../esb-toolkit/media/ch6-webservicetest.gif "Ch6-WebServiceTest")</span></span>  
  
 <span data-ttu-id="ed42a-110">**图 1**</span><span class="sxs-lookup"><span data-stu-id="ed42a-110">**Figure 1**</span></span>  
  
 <span data-ttu-id="ed42a-111">**BizTalk 操作 Web 服务测试客户端**</span><span class="sxs-lookup"><span data-stu-id="ed42a-111">**The BizTalk Operations Web Service Test Client**</span></span>  
  
 <span data-ttu-id="ed42a-112">若要执行不需要任何参数的 BizTalk 操作 Web 服务方法，只需单击左侧和右侧的应用程序窗口中的相应按钮。</span><span class="sxs-lookup"><span data-stu-id="ed42a-112">To execute a method of the BizTalk Operations Web service that does not require any parameters, simply click the appropriate button in the left side of the application window.</span></span> <span data-ttu-id="ed42a-113">对于需要输入的参数的方法在窗口顶部的下拉列表中选择的方法，输入参数值要求，然后依次**调用服务**按钮。</span><span class="sxs-lookup"><span data-stu-id="ed42a-113">For methods that do require input parameters, select the method in the drop-down list at the top of the window, enter the parameter values you require, and then click the **Invoke Service** button.</span></span>  
  
## <a name="how-the-sample-works"></a><span data-ttu-id="ed42a-114">示例工作原理</span><span class="sxs-lookup"><span data-stu-id="ed42a-114">How the Sample Works</span></span>  
 <span data-ttu-id="ed42a-115">示例应用程序实例化 ESB BizTalk 操作 Web 服务，并调用相应的方法，具体取决于应用程序中选择的设置。</span><span class="sxs-lookup"><span data-stu-id="ed42a-115">The sample application instantiates the ESB BizTalk Operations Web service and calls the appropriate method depending on the settings you select in the application.</span></span> <span data-ttu-id="ed42a-116">它将传递的值中输入应用程序控制作为参数给选定的服务方法，并从服务方法在应用程序窗口中显示收集输出。</span><span class="sxs-lookup"><span data-stu-id="ed42a-116">It passes the value(s) you enter in the application controls as parameters to the selected service method, and it collects the output from the service method to display in the application window.</span></span>