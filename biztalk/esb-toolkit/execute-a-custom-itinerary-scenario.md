---
title: 执行自定义路线方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6fd69e29-e853-4b16-9966-29ab98dd5bea
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9dc7b746f636b6f90462d296f12827fb0492dd23
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009550"
---
# <a name="execute-a-custom-itinerary-scenario"></a><span data-ttu-id="66c7c-102">执行自定义路线方案</span><span class="sxs-lookup"><span data-stu-id="66c7c-102">Execute a Custom Itinerary Scenario</span></span>
<span data-ttu-id="66c7c-103">可以使用路线测试客户端应用程序来执行自定义路线方案。</span><span class="sxs-lookup"><span data-stu-id="66c7c-103">You can use the Itinerary Test Client application execute custom itinerary scenarios.</span></span>  

### <a name="to-execute-a-custom-itinerary-scenario-using-the-itinerary-test-client-application"></a><span data-ttu-id="66c7c-104">若要执行使用路线测试客户端应用程序的自定义路线方案</span><span class="sxs-lookup"><span data-stu-id="66c7c-104">To execute a custom itinerary scenario using the Itinerary Test Client application</span></span>  

1. <span data-ttu-id="66c7c-105">在 Windows 资源管理器中打开文件夹 \Source\Samples\Itinerary\Source\ESB。安装位置的 Itinerary.Test\bin\Debug[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]示例和启动应用程序名为 Esb.Itinerary.Test.exe。</span><span class="sxs-lookup"><span data-stu-id="66c7c-105">In Windows Explorer, open the folder \Source\Samples\Itinerary\Source\ESB.Itinerary.Test\bin\Debug where you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] samples and start the application named Esb.Itinerary.Test.exe.</span></span>  

2. <span data-ttu-id="66c7c-106">选择中的服务类型**ServiceType**下拉列表中，为请求中，指定一个名称，然后选择**IsRequestResponse**复选框，如果这是请求/响应操作。</span><span class="sxs-lookup"><span data-stu-id="66c7c-106">Select a service type in the **ServiceType** drop-down list, specify a name for the request, and then select the **IsRequestResponse** check box if this is a request/response operation.</span></span> <span data-ttu-id="66c7c-107">可以指定双向操作，然后选择要使用路线 Web 服务; 的 WCF 版本若要执行此操作，请选择中的复选框**Web 服务选项**位于应用程序窗口的顶部部分。</span><span class="sxs-lookup"><span data-stu-id="66c7c-107">You can specify a two-way operation and choose to use the WCF version of the Itinerary Web service; to do this, select the check boxes in the **Web Service Options** section at the top of the application window.</span></span>  

3. <span data-ttu-id="66c7c-108">若要指定冲突解决程序以使用与中的所选服务**AddResolversfortheService**部分中的窗口中，选择冲突解决程序从下拉列表中，键入，然后单击**AddResolver**。</span><span class="sxs-lookup"><span data-stu-id="66c7c-108">To specify the resolvers to use with the selected service in the **AddResolversfortheService** section of the window, select a resolver type from the drop-down list, and then click **AddResolver**.</span></span> <span data-ttu-id="66c7c-109">如果需要，可以添加多个冲突解决程序。</span><span class="sxs-lookup"><span data-stu-id="66c7c-109">You can add more than one resolver if required.</span></span> <span data-ttu-id="66c7c-110">添加所有必需的冲突解决程序后，单击**AddService**按钮以将此服务调用添加到路线。</span><span class="sxs-lookup"><span data-stu-id="66c7c-110">After you add all the required resolvers, click the **AddService** button to add this service invocation to the itinerary.</span></span>  

4. <span data-ttu-id="66c7c-111">如果你想要将多个服务调用添加到路线，重复步骤 2 和 3。</span><span class="sxs-lookup"><span data-stu-id="66c7c-111">If you want to add more service invocations to the itinerary, repeat steps 2 and 3.</span></span> <span data-ttu-id="66c7c-112">此外可以使用**RemoveService**并**ClearServices**按钮可以修改的路线中的服务列表。</span><span class="sxs-lookup"><span data-stu-id="66c7c-112">You can also use the **RemoveService** and **ClearServices** buttons to modify the list of services in the itinerary.</span></span>  

5. <span data-ttu-id="66c7c-113">如果你想要另找时间重复当前路线，将保存完成当前的旅行计划到磁盘通过单击**SaveItinerary**按钮。</span><span class="sxs-lookup"><span data-stu-id="66c7c-113">If you want to repeat the current itinerary at another time, save the complete current itinerary to disk by clicking the **SaveItinerary** button.</span></span> <span data-ttu-id="66c7c-114">通过单击，可以再次加载它**LoadItinerary**按钮。</span><span class="sxs-lookup"><span data-stu-id="66c7c-114">You can load it again by clicking the **LoadItinerary** button.</span></span> <span data-ttu-id="66c7c-115">这意味着，不需要在路线中指定的服务和冲突解决程序，每次执行此方案中使用不同的消息或旅行计划的 Web 服务设置。</span><span class="sxs-lookup"><span data-stu-id="66c7c-115">This means that you do not have to specify the services and resolvers in the itinerary every time you execute this scenario with different messages or Itinerary Web service settings.</span></span>  

6. <span data-ttu-id="66c7c-116">加载适当的消息。</span><span class="sxs-lookup"><span data-stu-id="66c7c-116">Load a suitable message.</span></span> <span data-ttu-id="66c7c-117">若要执行此操作，或者键入路径和名称中的消息**LoadMessage**文本框或单击省略号按钮 （...），并选择所需的消息文件。</span><span class="sxs-lookup"><span data-stu-id="66c7c-117">To do this, either type the path and name of the message in the **LoadMessage** text box or click the ellipsis button (...), and then select the required message file.</span></span>  

7. <span data-ttu-id="66c7c-118">单击**SubmitRequest**按钮以提交对具有指定的路线设置进行处理的消息。</span><span class="sxs-lookup"><span data-stu-id="66c7c-118">Click the **SubmitRequest** button to submit the message for processing with the itinerary settings you specified.</span></span> <span data-ttu-id="66c7c-119">如果在处理返回的结果，这将显示在**结果**文本框。</span><span class="sxs-lookup"><span data-stu-id="66c7c-119">If the processing returns a result, this will appear in the **Result** text box.</span></span>
