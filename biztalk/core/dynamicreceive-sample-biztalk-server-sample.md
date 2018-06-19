---
title: DynamicReceive 示例 （BizTalk Server 示例） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0fa7c934-7ec3-45ad-b226-c8c53934ecb1
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e0dc620d2d12933d34df0dce9eb02b697871bdc
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972739"
---
# <a name="dynamicreceive-sample-biztalk-server-sample"></a><span data-ttu-id="deeda-102">DynamicReceive 示例（BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="deeda-102">DynamicReceive Sample (BizTalk Server Sample)</span></span>
<span data-ttu-id="deeda-103">DynamicReceive 示例演示如何接收[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]MQSeries 从消息队列时动态指定 MQSeries 队列的 URI。</span><span class="sxs-lookup"><span data-stu-id="deeda-103">The DynamicReceive sample demonstrates how to receive [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] messages from an MQSeries queue when the URI for the MQSeries queue is specified dynamically.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="deeda-104">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="deeda-104">What This Sample Does</span></span>  
 <span data-ttu-id="deeda-105">此示例将动态创建按指定的 MQSeries 队列**queueManager**，**队列**，和**服务器**变量。</span><span class="sxs-lookup"><span data-stu-id="deeda-105">This sample dynamically creates an MQSeries queue as specified by the **queueManager**, **queue**, and **server** variables.</span></span> <span data-ttu-id="deeda-106">它使动态接收方案，并获取[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]动态指定 MQSeries 队列中的消息基于中指定的筛选器条件**MQMD_MsgId**和**MQMD_CorrelId**消息属性。</span><span class="sxs-lookup"><span data-stu-id="deeda-106">It enables a dynamic receive scenario and obtains [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] messages from the dynamically specified MQSeries queue based on the filter criteria specified in the **MQMD_MsgId** and **MQMD_CorrelId** message properties.</span></span>  
  
## <a name="how-this-sample-was-designed-and-why"></a><span data-ttu-id="deeda-107">本示例的设计方式和原因</span><span class="sxs-lookup"><span data-stu-id="deeda-107">How This Sample Was Designed and Why</span></span>  
 <span data-ttu-id="deeda-108">通过在业务流程中指定 MQSeries 队列的 URI 地址，MQSeries 适配器即可从该队列动态接收消息。</span><span class="sxs-lookup"><span data-stu-id="deeda-108">The MQSeries adapter can dynamically receive messages from an MQSeries queue by specifying the URI address of the queue in the orchestration.</span></span> <span data-ttu-id="deeda-109">此功能可通过在业务流程中使用要求-响应发送端口来获得。</span><span class="sxs-lookup"><span data-stu-id="deeda-109">This functionality is achieved by using a solicit-response send port in the orchestration.</span></span>  
  
 <span data-ttu-id="deeda-110">若要动态接收消息，指定下列各项中的**表达式**形状中业务流程：</span><span class="sxs-lookup"><span data-stu-id="deeda-110">To dynamically receive messages, specify the following in an **Expression** shape in the orchestration:</span></span>  
  
1.  <span data-ttu-id="deeda-111">启用动态接收通过设置以下属性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]消息： **MQSeries.DynamicReceive** = `'Yes'`</span><span class="sxs-lookup"><span data-stu-id="deeda-111">Enable dynamic receive by setting the following property on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] message: **MQSeries.DynamicReceive** = `'Yes'`</span></span>  
  
2.  <span data-ttu-id="deeda-112">指定要从其中获取通过设置 URI 的端口的消息的地址。</span><span class="sxs-lookup"><span data-stu-id="deeda-112">Specify the address from which to get the messages by setting the port URI.</span></span> <span data-ttu-id="deeda-113">（可选） 你可以指定以下项：</span><span class="sxs-lookup"><span data-stu-id="deeda-113">Optionally you can specify the following:</span></span>  
  
    -   <span data-ttu-id="deeda-114">指定在使用中获取消息之前的等待间隔**MQSeries.WaitInterval**对消息的属性。</span><span class="sxs-lookup"><span data-stu-id="deeda-114">Specify the wait interval before getting the messages by using the **MQSeries.WaitInterval** property on the message.</span></span>  
  
    -   <span data-ttu-id="deeda-115">指定用于接收消息的匹配条件。</span><span class="sxs-lookup"><span data-stu-id="deeda-115">Specify match criteria for receiving messages.</span></span> <span data-ttu-id="deeda-116">匹配条件选项包括**消息 ID**， **CorrelationID**， **GroupID**，和**MessageSequenceNumber**。</span><span class="sxs-lookup"><span data-stu-id="deeda-116">The match criteria options are **Message ID**, **CorrelationID**, **GroupID**, and **MessageSequenceNumber**.</span></span> <span data-ttu-id="deeda-117">请参阅"属性相关到 BizTalk Server"，网址[http://go.microsoft.com/fwlink/?LinkId=89396](http://go.microsoft.com/fwlink/?LinkId=89396)有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="deeda-117">See "Properties Related to BizTalk Server" at [http://go.microsoft.com/fwlink/?LinkId=89396](http://go.microsoft.com/fwlink/?LinkId=89396) for more details.</span></span>  
  
 <span data-ttu-id="deeda-118">使用这些属性创建消息后它是使用请求-响应发送端口发送到 MQSeries 队列。</span><span class="sxs-lookup"><span data-stu-id="deeda-118">After the message is created with these properties it is sent to the MQSeries queue by using a solicit-response send port.</span></span> <span data-ttu-id="deeda-119">端口指定的适配器，从指定的 URI 指定的匹配选项接收消息。</span><span class="sxs-lookup"><span data-stu-id="deeda-119">The port specifies the adapter to receive messages from the specified URI with the indicated match options.</span></span> <span data-ttu-id="deeda-120">下面的操作结果：</span><span class="sxs-lookup"><span data-stu-id="deeda-120">The following actions result:</span></span>  
  
-   <span data-ttu-id="deeda-121">如果满足筛选条件，以获取一条消息，消息从队列检索，并且在发送回业务流程。</span><span class="sxs-lookup"><span data-stu-id="deeda-121">If the filter criteria to obtain a message are satisfied, then the message is retrieved from the queue and is sent back to the orchestration.</span></span>  
  
-   <span data-ttu-id="deeda-122">如果不满足筛选条件，以获取一条消息，则返回 dummy 响应。</span><span class="sxs-lookup"><span data-stu-id="deeda-122">If the filter criteria to obtain a message are not satisfied, a dummy response is returned.</span></span> <span data-ttu-id="deeda-123">这是指示指定的选项未返回任何消息从队列。</span><span class="sxs-lookup"><span data-stu-id="deeda-123">This is an indication that the specified options did not return any messages from the queue.</span></span>  
  
 <span data-ttu-id="deeda-124">使用动态接收更加灵活地因为固定接收位置不是必需的功能提供。</span><span class="sxs-lookup"><span data-stu-id="deeda-124">Using the dynamic receive functionality gives you additional flexibility because a fixed receive location is not required.</span></span> <span data-ttu-id="deeda-125">在某些情况下，可能不知道直到运行时的 URI。</span><span class="sxs-lookup"><span data-stu-id="deeda-125">In some cases, you may not know the URI until run time.</span></span> <span data-ttu-id="deeda-126">动态接收功能可以动态确定从何处获取消息。</span><span class="sxs-lookup"><span data-stu-id="deeda-126">Dynamic receive functionality allows you to dynamically determine from where to obtain messages.</span></span> <span data-ttu-id="deeda-127">它还意味着不需要实现业务流程中的排队协定。</span><span class="sxs-lookup"><span data-stu-id="deeda-127">It also means you do not need to implement a queuing contract within an orchestration.</span></span>  <span data-ttu-id="deeda-128">您可以等待使用动态指定的 URI 从基于指定的匹配条件 MQSeries 队列获取消息。</span><span class="sxs-lookup"><span data-stu-id="deeda-128">You can wait to obtain messages by using a dynamically specified URI from the MQSeries queue based on the specified match criteria.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="deeda-129">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="deeda-129">Where to Find This Sample</span></span>  
 <span data-ttu-id="deeda-130">\<*示例路径*\>\Samples\AdaptersUsage\MQSeriesAdapter\DynamicReceive</span><span class="sxs-lookup"><span data-stu-id="deeda-130">\<*Samples Path*\>\Samples\AdaptersUsage\MQSeriesAdapter\DynamicReceive</span></span>  
  
 <span data-ttu-id="deeda-131">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="deeda-131">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="deeda-132">文件</span><span class="sxs-lookup"><span data-stu-id="deeda-132">File</span></span>|<span data-ttu-id="deeda-133">Description</span><span class="sxs-lookup"><span data-stu-id="deeda-133">Description</span></span>|  
|<span data-ttu-id="deeda-134">DynamicReceive.btproj，</span><span class="sxs-lookup"><span data-stu-id="deeda-134">DynamicReceive.btproj,</span></span><br /><br /> <span data-ttu-id="deeda-135">DynamicReceive.sln</span><span class="sxs-lookup"><span data-stu-id="deeda-135">DynamicReceive.sln</span></span>|<span data-ttu-id="deeda-136">应用程序的项目和解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="deeda-136">Project and solution files for the application.</span></span>|  
|<span data-ttu-id="deeda-137">DynamicReceive e.odx</span><span class="sxs-lookup"><span data-stu-id="deeda-137">DynamicReceive e.odx</span></span>|<span data-ttu-id="deeda-138">应用程序的 BizTalk 业务流程文件。</span><span class="sxs-lookup"><span data-stu-id="deeda-138">The BizTalk orchestration file for the application.</span></span>|  
|<span data-ttu-id="deeda-139">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="deeda-139">Setup.bat</span></span>|<span data-ttu-id="deeda-140">要创建的密钥文件，编译该项目，并将其部署的批处理文件。</span><span class="sxs-lookup"><span data-stu-id="deeda-140">Batch file to create the key file, compile the project, and deploy it.</span></span>|  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="deeda-141">如何使用本示例</span><span class="sxs-lookup"><span data-stu-id="deeda-141">How to Use This Sample</span></span>  
 <span data-ttu-id="deeda-142">指定**Microsoft.XLANGs.BaseTypes.Address**适合你的解决方案。</span><span class="sxs-lookup"><span data-stu-id="deeda-142">Specify the **Microsoft.XLANGs.BaseTypes.Address** that makes sense for your solution.</span></span> <span data-ttu-id="deeda-143">更改**MQSeries.WaitInterval**指定如果您希望接收响应消息。</span><span class="sxs-lookup"><span data-stu-id="deeda-143">Change the **MQSeries.WaitInterval** to specify when you expect to receive the response messages.</span></span> <span data-ttu-id="deeda-144">更新 （或添加） 的匹配选项，或将其删除，如果你打算获取所有消息。</span><span class="sxs-lookup"><span data-stu-id="deeda-144">Update (or add) the match options, or remove them if you plan to obtain all messages.</span></span>  
  
## <a name="building-and-running-the-sample"></a><span data-ttu-id="deeda-145">生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="deeda-145">Building and Running the Sample</span></span>  
  
#### <a name="to-create-the-sample"></a><span data-ttu-id="deeda-146">若要创建示例</span><span class="sxs-lookup"><span data-stu-id="deeda-146">To create the sample</span></span>  
  
1.  <span data-ttu-id="deeda-147">在 Microsoft 中创建新的业务流程项目[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="deeda-147">Create a new orchestration project in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="deeda-148">启用动态接收操作，通过设置**MQSeries.DynamicReceive**属性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]消息`'Yes'`。</span><span class="sxs-lookup"><span data-stu-id="deeda-148">Enable the dynamic receive operation by setting the **MQSeries.DynamicReceive** property on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] message to `'Yes'`.</span></span>  
  
3.  <span data-ttu-id="deeda-149">指定要从中获取消息通过设置地址**端口 URI**。</span><span class="sxs-lookup"><span data-stu-id="deeda-149">Specify the address from which to obtain the messages by setting the **Port URI**.</span></span>  
  
4.  <span data-ttu-id="deeda-150">（可选） 可以指定以下两个属性：</span><span class="sxs-lookup"><span data-stu-id="deeda-150">Optionally the following two properties can be specified:</span></span>  
  
    1.  <span data-ttu-id="deeda-151">指定在使用中获取消息之前的等待间隔**MQSeries.WaitInterval**对消息的属性。</span><span class="sxs-lookup"><span data-stu-id="deeda-151">Specify a wait interval before getting the messages by using the **MQSeries.WaitInterval** property on the message.</span></span>  
  
    2.  <span data-ttu-id="deeda-152">指定用于接收消息的匹配条件。</span><span class="sxs-lookup"><span data-stu-id="deeda-152">Specify match criteria for receiving messages.</span></span> <span data-ttu-id="deeda-153">有关详细信息，请参阅“匹配选项”帮助。</span><span class="sxs-lookup"><span data-stu-id="deeda-153">See "Match options" help for more details.</span></span>  
  
5.  <span data-ttu-id="deeda-154">更改业务流程，以指定要从中获取从消息中的以下变量：</span><span class="sxs-lookup"><span data-stu-id="deeda-154">Change the following variables in the orchestration to specify where to get the messages from:</span></span>  
  
    -   <span data-ttu-id="deeda-155">**队列**， **queueManager**，和**服务器**。</span><span class="sxs-lookup"><span data-stu-id="deeda-155">**Queue**, **queueManager**, and **server**.</span></span> <span data-ttu-id="deeda-156">这些凭据用于进行中生成 URI**表达式**形状。</span><span class="sxs-lookup"><span data-stu-id="deeda-156">These are used to build the URI in the **Expression** shape.</span></span>  
  
6.  <span data-ttu-id="deeda-157">修改**表达式**形状以根据需要注释掉动态队列创建和匹配选项。</span><span class="sxs-lookup"><span data-stu-id="deeda-157">Modify the **Expression** shape to comment out dynamic queue creation and match options as necessary.</span></span>  
  
7.  <span data-ttu-id="deeda-158">你可以生成和部署中通过以下方式之一的项目：</span><span class="sxs-lookup"><span data-stu-id="deeda-158">You can build and deploy the project in either of the following ways:</span></span>  
  
    -   <span data-ttu-id="deeda-159">打开解决方案，右键单击解决方案资源管理器中的项目，单击**属性**查看项目属性。</span><span class="sxs-lookup"><span data-stu-id="deeda-159">Open the solution, right click the project in Solution explorer and click **Properties** to view project properties.</span></span> <span data-ttu-id="deeda-160">在签名选项卡上单击**\<新建...\>** 中**选择强名称密钥文件**下拉框。</span><span class="sxs-lookup"><span data-stu-id="deeda-160">On the Signing tab click **\<New...\>** in the **Choose a strong name key file** drop down box.</span></span> <span data-ttu-id="deeda-161">然后提供密钥文件名称，并部署。</span><span class="sxs-lookup"><span data-stu-id="deeda-161">Then provide a key file name and deploy.</span></span>  
  
    -   <span data-ttu-id="deeda-162">或者，运行 setup.bat 文件，它创建的密钥文件，生成项目并将其部署。</span><span class="sxs-lookup"><span data-stu-id="deeda-162">Alternatively, run the setup.bat file which creates the key file, builds the project and deploys it.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="deeda-163">运行示例</span><span class="sxs-lookup"><span data-stu-id="deeda-163">To run the sample</span></span>  
  
1.  <span data-ttu-id="deeda-164">将业务流程绑定到 BizTalk 主机。</span><span class="sxs-lookup"><span data-stu-id="deeda-164">Bind the orchestration to the BizTalk Host.</span></span>  
  
2.  <span data-ttu-id="deeda-165">启用业务流程创建的文件接收端口。</span><span class="sxs-lookup"><span data-stu-id="deeda-165">Enable the file receive port created by the orchestration.</span></span> <span data-ttu-id="deeda-166">更改文件接收位置从**c:\temp\in**到适当的文件文件夹。</span><span class="sxs-lookup"><span data-stu-id="deeda-166">Change the file receive location from **c:\temp\in** to the proper file folder.</span></span>  
  
3.  <span data-ttu-id="deeda-167">登记并启动已创建的两个发送端口。</span><span class="sxs-lookup"><span data-stu-id="deeda-167">Enlist and start the two send ports that were created.</span></span> <span data-ttu-id="deeda-168">一个端口是动态要求响应端口类型，另一个是文件发送端口且是用于发送消息的队列。</span><span class="sxs-lookup"><span data-stu-id="deeda-168">One port is a dynamic solicit-response port type, while the other is a file send port and is the queue where the message will be sent.</span></span> <span data-ttu-id="deeda-169">确保已将此设置为正确的位置。</span><span class="sxs-lookup"><span data-stu-id="deeda-169">Ensure that this is set to the correct location.</span></span>  
  
4.  <span data-ttu-id="deeda-170">若要启动该业务流程，请将一个文件放在输入文件夹中。</span><span class="sxs-lookup"><span data-stu-id="deeda-170">To start the orchestration, drop a file in the input folder.</span></span> <span data-ttu-id="deeda-171">这将调用的 MQSeries 适配器和调用**MQSAgent2**上指定的服务器，以获取消息的 COM + 组件。</span><span class="sxs-lookup"><span data-stu-id="deeda-171">This invokes the MQSeries adapter and calls the **MQSAgent2** COM+ component on the specified server to obtain the message.</span></span> <span data-ttu-id="deeda-172">接收到的消息将存储在文件发送端口中指定的文件夹位置。</span><span class="sxs-lookup"><span data-stu-id="deeda-172">The received message appears in the folder location specified in the file send port.</span></span>  
  
5.  <span data-ttu-id="deeda-173">如果未找到消息中指定的条件匹配的**表达式**形状，dummy 消息放入输出文件夹。</span><span class="sxs-lookup"><span data-stu-id="deeda-173">If no message is found that matches the criteria specified in the **Expression** shape, a dummy message is dropped into the output folder.</span></span> <span data-ttu-id="deeda-174">若要禁用匹配选项，注释掉中的最后两行**表达式**形状。</span><span class="sxs-lookup"><span data-stu-id="deeda-174">To disable match options, comment out the last two lines in the **Expression** shape.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="deeda-175">注释</span><span class="sxs-lookup"><span data-stu-id="deeda-175">Comments</span></span>  
  
-   <span data-ttu-id="deeda-176">如果正在动态创建队列但未删除，则该队列将在下一个业务流程实例激活时引发错误。</span><span class="sxs-lookup"><span data-stu-id="deeda-176">If the queue is being dynamically created, but not deleted, it will result in errors when the next orchestration instance is activated.</span></span>  
  
-   <span data-ttu-id="deeda-177">还可通过其他方法动态设置 URI，此示例只指定了一个选项。</span><span class="sxs-lookup"><span data-stu-id="deeda-177">There are other ways to set the URI dynamically; this sample specifies just one option.</span></span> <span data-ttu-id="deeda-178">例如，可在消息上下文中读取某些属性来设置 URI。</span><span class="sxs-lookup"><span data-stu-id="deeda-178">For example, the URI could be set by reading some property in the message context.</span></span>  
  
-   <span data-ttu-id="deeda-179">如果队列中没有满足匹配选项的消息，则将返回一个虚拟消息。</span><span class="sxs-lookup"><span data-stu-id="deeda-179">If there are no messages in the queue that satisfy the match options, a dummy message is returned.</span></span>  
  
-   <span data-ttu-id="deeda-180">由于此示例使用动态发送端口，因此，可能需要指定诸如重试和事务等其他选项。</span><span class="sxs-lookup"><span data-stu-id="deeda-180">Because this sample uses dynamic send ports, other options may need to be specified, such as retry and transactions.</span></span> <span data-ttu-id="deeda-181">使用由适配器公开的上下文属性，可在将消息发送到动态要求-响应端口前设置这些选项。</span><span class="sxs-lookup"><span data-stu-id="deeda-181">Use the context properties exposed by the adapter to set these options before sending the message out to the dynamic solicit-response port.</span></span>  
  
-   <span data-ttu-id="deeda-182">可以创建和使用动态删除 MQSeries 队列**MQSAdapterAdmin2**接口。</span><span class="sxs-lookup"><span data-stu-id="deeda-182">MQSeries queues can be created and deleted dynamically by using the **MQSAdapterAdmin2** interface.</span></span> <span data-ttu-id="deeda-183">如何动态创建 MQSeries 队列的示例，请参阅"支持适用于队列管理"网址[http://go.microsoft.com/fwlink/?LinkId=89400](http://go.microsoft.com/fwlink/?LinkId=89400)。</span><span class="sxs-lookup"><span data-stu-id="deeda-183">For an example of how to dynamically create MQSeries queues, see "Support for Queue Management" at [http://go.microsoft.com/fwlink/?LinkId=89400](http://go.microsoft.com/fwlink/?LinkId=89400).</span></span>