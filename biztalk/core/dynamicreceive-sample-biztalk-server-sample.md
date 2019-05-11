---
title: DynamicReceive 示例 （BizTalk Server 示例） |Microsoft Docs
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
ms.openlocfilehash: 38cde24f8bc91fc5a2fc741978ebfac9d7283c51
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350612"
---
# <a name="dynamicreceive-sample-biztalk-server-sample"></a><span data-ttu-id="c15ac-102">DynamicReceive 示例 （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="c15ac-102">DynamicReceive Sample (BizTalk Server Sample)</span></span>
<span data-ttu-id="c15ac-103">DynamicReceive 示例演示如何接收[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]来自 MQSeries 的消息队列时动态指定 MQSeries 队列的 URI。</span><span class="sxs-lookup"><span data-stu-id="c15ac-103">The DynamicReceive sample demonstrates how to receive [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] messages from an MQSeries queue when the URI for the MQSeries queue is specified dynamically.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="c15ac-104">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="c15ac-104">What This Sample Does</span></span>  
 <span data-ttu-id="c15ac-105">此示例将动态创建 MQSeries 队列由指定**queueManager**，**队列**，并**server**变量。</span><span class="sxs-lookup"><span data-stu-id="c15ac-105">This sample dynamically creates an MQSeries queue as specified by the **queueManager**, **queue**, and **server** variables.</span></span> <span data-ttu-id="c15ac-106">启用动态接收方案并获取[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]动态指定 MQSeries 队列中的消息基于中指定的筛选器条件**MQMD_MsgId**并**MQMD_CorrelId**消息属性。</span><span class="sxs-lookup"><span data-stu-id="c15ac-106">It enables a dynamic receive scenario and obtains [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] messages from the dynamically specified MQSeries queue based on the filter criteria specified in the **MQMD_MsgId** and **MQMD_CorrelId** message properties.</span></span>  
  
## <a name="how-this-sample-was-designed-and-why"></a><span data-ttu-id="c15ac-107">此示例设计的方式和原因</span><span class="sxs-lookup"><span data-stu-id="c15ac-107">How This Sample Was Designed and Why</span></span>  
 <span data-ttu-id="c15ac-108">MQSeries 适配器可以在业务流程中指定的队列的 URI 地址动态从 MQSeries 队列接收消息。</span><span class="sxs-lookup"><span data-stu-id="c15ac-108">The MQSeries adapter can dynamically receive messages from an MQSeries queue by specifying the URI address of the queue in the orchestration.</span></span> <span data-ttu-id="c15ac-109">通过使用要求响应发送端口业务流程中的实现此功能。</span><span class="sxs-lookup"><span data-stu-id="c15ac-109">This functionality is achieved by using a solicit-response send port in the orchestration.</span></span>  
  
 <span data-ttu-id="c15ac-110">若要动态接收消息，指定以下**表达式**形状在业务流程中：</span><span class="sxs-lookup"><span data-stu-id="c15ac-110">To dynamically receive messages, specify the following in an **Expression** shape in the orchestration:</span></span>  
  
1. <span data-ttu-id="c15ac-111">启用动态接收通过设置以下属性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]消息：**MQSeries.DynamicReceive** = `'Yes'`</span><span class="sxs-lookup"><span data-stu-id="c15ac-111">Enable dynamic receive by setting the following property on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] message: **MQSeries.DynamicReceive** = `'Yes'`</span></span>  
  
2. <span data-ttu-id="c15ac-112">指定要从其中获取消息通过设置 URI 的端口地址。</span><span class="sxs-lookup"><span data-stu-id="c15ac-112">Specify the address from which to get the messages by setting the port URI.</span></span> <span data-ttu-id="c15ac-113">（可选） 你可以指定以下项：</span><span class="sxs-lookup"><span data-stu-id="c15ac-113">Optionally you can specify the following:</span></span>  
  
   -   <span data-ttu-id="c15ac-114">使用获取消息之前指定的等待时间间隔**MQSeries.WaitInterval**消息属性。</span><span class="sxs-lookup"><span data-stu-id="c15ac-114">Specify the wait interval before getting the messages by using the **MQSeries.WaitInterval** property on the message.</span></span>  
  
   -   <span data-ttu-id="c15ac-115">指定用于接收消息的匹配条件。</span><span class="sxs-lookup"><span data-stu-id="c15ac-115">Specify match criteria for receiving messages.</span></span> <span data-ttu-id="c15ac-116">匹配条件选项包括**消息 ID**， **CorrelationID**， **GroupID**，以及**MessageSequenceNumber**。</span><span class="sxs-lookup"><span data-stu-id="c15ac-116">The match criteria options are **Message ID**, **CorrelationID**, **GroupID**, and **MessageSequenceNumber**.</span></span> <span data-ttu-id="c15ac-117">请参阅"属性相关到 BizTalk Server"，网址[ http://go.microsoft.com/fwlink/?LinkId=89396 ](http://go.microsoft.com/fwlink/?LinkId=89396)的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="c15ac-117">See "Properties Related to BizTalk Server" at [http://go.microsoft.com/fwlink/?LinkId=89396](http://go.microsoft.com/fwlink/?LinkId=89396) for more details.</span></span>  
  
   <span data-ttu-id="c15ac-118">将创建具有这些属性的消息后它是使用要求响应发送端口发送到 MQSeries 队列。</span><span class="sxs-lookup"><span data-stu-id="c15ac-118">After the message is created with these properties it is sent to the MQSeries queue by using a solicit-response send port.</span></span> <span data-ttu-id="c15ac-119">端口指定从指定的 URI 所指示的匹配选项接收消息的适配器。</span><span class="sxs-lookup"><span data-stu-id="c15ac-119">The port specifies the adapter to receive messages from the specified URI with the indicated match options.</span></span> <span data-ttu-id="c15ac-120">下面的操作结果：</span><span class="sxs-lookup"><span data-stu-id="c15ac-120">The following actions result:</span></span>  
  
- <span data-ttu-id="c15ac-121">如果满足筛选条件来获取一条消息，消息从队列检索，并且发送回业务流程。</span><span class="sxs-lookup"><span data-stu-id="c15ac-121">If the filter criteria to obtain a message are satisfied, then the message is retrieved from the queue and is sent back to the orchestration.</span></span>  
  
- <span data-ttu-id="c15ac-122">如果不满足筛选条件来获取一条消息，则返回一个虚拟响应。</span><span class="sxs-lookup"><span data-stu-id="c15ac-122">If the filter criteria to obtain a message are not satisfied, a dummy response is returned.</span></span> <span data-ttu-id="c15ac-123">这是指定的选项未返回任何消息队列中的指示。</span><span class="sxs-lookup"><span data-stu-id="c15ac-123">This is an indication that the specified options did not return any messages from the queue.</span></span>  
  
  <span data-ttu-id="c15ac-124">使用动态接收更加灵活地因为固定的接收位置不是必需的功能提供。</span><span class="sxs-lookup"><span data-stu-id="c15ac-124">Using the dynamic receive functionality gives you additional flexibility because a fixed receive location is not required.</span></span> <span data-ttu-id="c15ac-125">在某些情况下，可能不知道到运行时的 URI。</span><span class="sxs-lookup"><span data-stu-id="c15ac-125">In some cases, you may not know the URI until run time.</span></span> <span data-ttu-id="c15ac-126">动态接收功能，您可以动态确定从何处可以获取消息。</span><span class="sxs-lookup"><span data-stu-id="c15ac-126">Dynamic receive functionality allows you to dynamically determine from where to obtain messages.</span></span> <span data-ttu-id="c15ac-127">这还意味着不需要实现业务流程中的排队协定。</span><span class="sxs-lookup"><span data-stu-id="c15ac-127">It also means you do not need to implement a queuing contract within an orchestration.</span></span>  <span data-ttu-id="c15ac-128">你可以等待可以通过使用动态指定从指定的匹配条件的 MQSeries 队列的 URI 中获取消息。</span><span class="sxs-lookup"><span data-stu-id="c15ac-128">You can wait to obtain messages by using a dynamically specified URI from the MQSeries queue based on the specified match criteria.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="c15ac-129">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="c15ac-129">Where to Find This Sample</span></span>  
 <span data-ttu-id="c15ac-130">\<*Samples Path*\>\Samples\AdaptersUsage\MQSeriesAdapter\DynamicReceive</span><span class="sxs-lookup"><span data-stu-id="c15ac-130">\<*Samples Path*\>\Samples\AdaptersUsage\MQSeriesAdapter\DynamicReceive</span></span>  
  
 <span data-ttu-id="c15ac-131">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="c15ac-131">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c15ac-132">文件</span><span class="sxs-lookup"><span data-stu-id="c15ac-132">File</span></span>|<span data-ttu-id="c15ac-133">Description</span><span class="sxs-lookup"><span data-stu-id="c15ac-133">Description</span></span>|  
|<span data-ttu-id="c15ac-134">DynamicReceive.btproj,</span><span class="sxs-lookup"><span data-stu-id="c15ac-134">DynamicReceive.btproj,</span></span><br /><br /> <span data-ttu-id="c15ac-135">DynamicReceive.sln</span><span class="sxs-lookup"><span data-stu-id="c15ac-135">DynamicReceive.sln</span></span>|<span data-ttu-id="c15ac-136">应用程序的项目和解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="c15ac-136">Project and solution files for the application.</span></span>|  
|<span data-ttu-id="c15ac-137">DynamicReceive e.odx</span><span class="sxs-lookup"><span data-stu-id="c15ac-137">DynamicReceive e.odx</span></span>|<span data-ttu-id="c15ac-138">应用程序的 BizTalk 业务流程文件。</span><span class="sxs-lookup"><span data-stu-id="c15ac-138">The BizTalk orchestration file for the application.</span></span>|  
|<span data-ttu-id="c15ac-139">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="c15ac-139">Setup.bat</span></span>|<span data-ttu-id="c15ac-140">若要创建的密钥文件、 编译该项目，并将其部署的批处理文件。</span><span class="sxs-lookup"><span data-stu-id="c15ac-140">Batch file to create the key file, compile the project, and deploy it.</span></span>|  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="c15ac-141">如何使用此示例</span><span class="sxs-lookup"><span data-stu-id="c15ac-141">How to Use This Sample</span></span>  
 <span data-ttu-id="c15ac-142">指定**Microsoft.XLANGs.BaseTypes.Address**适合你的解决方案。</span><span class="sxs-lookup"><span data-stu-id="c15ac-142">Specify the **Microsoft.XLANGs.BaseTypes.Address** that makes sense for your solution.</span></span> <span data-ttu-id="c15ac-143">更改**MQSeries.WaitInterval**以指定希望接收响应消息。</span><span class="sxs-lookup"><span data-stu-id="c15ac-143">Change the **MQSeries.WaitInterval** to specify when you expect to receive the response messages.</span></span> <span data-ttu-id="c15ac-144">更新 （或添加） 的匹配选项，或删除它们，如果你打算中获取所有消息。</span><span class="sxs-lookup"><span data-stu-id="c15ac-144">Update (or add) the match options, or remove them if you plan to obtain all messages.</span></span>  
  
## <a name="building-and-running-the-sample"></a><span data-ttu-id="c15ac-145">构建和运行示例</span><span class="sxs-lookup"><span data-stu-id="c15ac-145">Building and Running the Sample</span></span>  
  
#### <a name="to-create-the-sample"></a><span data-ttu-id="c15ac-146">若要创建示例</span><span class="sxs-lookup"><span data-stu-id="c15ac-146">To create the sample</span></span>  
  
1. <span data-ttu-id="c15ac-147">在 Microsoft 中创建一个新的业务流程项目[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c15ac-147">Create a new orchestration project in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
2. <span data-ttu-id="c15ac-148">通过设置可启用动态接收操作**MQSeries.DynamicReceive**上的属性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]消息到`'Yes'`。</span><span class="sxs-lookup"><span data-stu-id="c15ac-148">Enable the dynamic receive operation by setting the **MQSeries.DynamicReceive** property on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] message to `'Yes'`.</span></span>  
  
3. <span data-ttu-id="c15ac-149">指定要从中获取消息的设置的地址**端口 URI**。</span><span class="sxs-lookup"><span data-stu-id="c15ac-149">Specify the address from which to obtain the messages by setting the **Port URI**.</span></span>  
  
4. <span data-ttu-id="c15ac-150">（可选） 可以指定以下两个属性：</span><span class="sxs-lookup"><span data-stu-id="c15ac-150">Optionally the following two properties can be specified:</span></span>  
  
   1.  <span data-ttu-id="c15ac-151">使用获取消息之前，指定等待间隔**MQSeries.WaitInterval**消息属性。</span><span class="sxs-lookup"><span data-stu-id="c15ac-151">Specify a wait interval before getting the messages by using the **MQSeries.WaitInterval** property on the message.</span></span>  
  
   2.  <span data-ttu-id="c15ac-152">指定用于接收消息的匹配条件。</span><span class="sxs-lookup"><span data-stu-id="c15ac-152">Specify match criteria for receiving messages.</span></span> <span data-ttu-id="c15ac-153">请参阅"匹配选项"更多详细信息的帮助。</span><span class="sxs-lookup"><span data-stu-id="c15ac-153">See "Match options" help for more details.</span></span>  
  
5. <span data-ttu-id="c15ac-154">更改业务流程，以指定从中获取从消息中的以下变量：</span><span class="sxs-lookup"><span data-stu-id="c15ac-154">Change the following variables in the orchestration to specify where to get the messages from:</span></span>  
  
   -   <span data-ttu-id="c15ac-155">**队列**， **queueManager**，和**server**。</span><span class="sxs-lookup"><span data-stu-id="c15ac-155">**Queue**, **queueManager**, and **server**.</span></span> <span data-ttu-id="c15ac-156">这些用于生成该 URI**表达式**形状。</span><span class="sxs-lookup"><span data-stu-id="c15ac-156">These are used to build the URI in the **Expression** shape.</span></span>  
  
6. <span data-ttu-id="c15ac-157">修改**表达式**形状中，以根据需要添加注释动态队列创建和匹配选项。</span><span class="sxs-lookup"><span data-stu-id="c15ac-157">Modify the **Expression** shape to comment out dynamic queue creation and match options as necessary.</span></span>  
  
7. <span data-ttu-id="c15ac-158">可生成和部署项目中，以下两种方式：</span><span class="sxs-lookup"><span data-stu-id="c15ac-158">You can build and deploy the project in either of the following ways:</span></span>  
  
   -   <span data-ttu-id="c15ac-159">打开解决方案，右键单击解决方案资源管理器中的项目，然后单击**属性**查看项目属性。</span><span class="sxs-lookup"><span data-stu-id="c15ac-159">Open the solution, right click the project in Solution explorer and click **Properties** to view project properties.</span></span> <span data-ttu-id="c15ac-160">在签名选项卡上单击**\<新建...\>** 中**选择一个强名称密钥文件**下拉框。</span><span class="sxs-lookup"><span data-stu-id="c15ac-160">On the Signing tab click **\<New...\>** in the **Choose a strong name key file** drop down box.</span></span> <span data-ttu-id="c15ac-161">然后提供密钥文件名称和部署。</span><span class="sxs-lookup"><span data-stu-id="c15ac-161">Then provide a key file name and deploy.</span></span>  
  
   -   <span data-ttu-id="c15ac-162">或者，运行 setup.bat 文件创建密钥文件，生成项目，并将其部署。</span><span class="sxs-lookup"><span data-stu-id="c15ac-162">Alternatively, run the setup.bat file which creates the key file, builds the project and deploys it.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="c15ac-163">若要运行示例</span><span class="sxs-lookup"><span data-stu-id="c15ac-163">To run the sample</span></span>  
  
1.  <span data-ttu-id="c15ac-164">将业务流程绑定到的 BizTalk 主机。</span><span class="sxs-lookup"><span data-stu-id="c15ac-164">Bind the orchestration to the BizTalk Host.</span></span>  
  
2.  <span data-ttu-id="c15ac-165">启用文件接收端口创建的业务流程。</span><span class="sxs-lookup"><span data-stu-id="c15ac-165">Enable the file receive port created by the orchestration.</span></span> <span data-ttu-id="c15ac-166">将文件接收位置从**c:\temp\in**到正确的文件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="c15ac-166">Change the file receive location from **c:\temp\in** to the proper file folder.</span></span>  
  
3.  <span data-ttu-id="c15ac-167">登记并启动已创建两个发送端口。</span><span class="sxs-lookup"><span data-stu-id="c15ac-167">Enlist and start the two send ports that were created.</span></span> <span data-ttu-id="c15ac-168">一个端口是动态要求响应端口类型，而其他是 file 发送端口，是队列发送消息。</span><span class="sxs-lookup"><span data-stu-id="c15ac-168">One port is a dynamic solicit-response port type, while the other is a file send port and is the queue where the message will be sent.</span></span> <span data-ttu-id="c15ac-169">请确保此值设置为正确的位置。</span><span class="sxs-lookup"><span data-stu-id="c15ac-169">Ensure that this is set to the correct location.</span></span>  
  
4.  <span data-ttu-id="c15ac-170">若要启动业务流程，请输入文件夹中删除文件。</span><span class="sxs-lookup"><span data-stu-id="c15ac-170">To start the orchestration, drop a file in the input folder.</span></span> <span data-ttu-id="c15ac-171">这将调用 MQSeries 适配器并调用**MQSAgent2** COM + 组件上指定的服务器以获取消息。</span><span class="sxs-lookup"><span data-stu-id="c15ac-171">This invokes the MQSeries adapter and calls the **MQSAgent2** COM+ component on the specified server to obtain the message.</span></span> <span data-ttu-id="c15ac-172">收到的消息出现在 file 发送端口中指定的文件夹位置。</span><span class="sxs-lookup"><span data-stu-id="c15ac-172">The received message appears in the folder location specified in the file send port.</span></span>  
  
5.  <span data-ttu-id="c15ac-173">如果未找到消息中指定的条件匹配的**表达式**形状，一个虚拟消息放入输出文件夹。</span><span class="sxs-lookup"><span data-stu-id="c15ac-173">If no message is found that matches the criteria specified in the **Expression** shape, a dummy message is dropped into the output folder.</span></span> <span data-ttu-id="c15ac-174">若要禁用匹配选项，将最后两个行中注释掉**表达式**形状。</span><span class="sxs-lookup"><span data-stu-id="c15ac-174">To disable match options, comment out the last two lines in the **Expression** shape.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="c15ac-175">注释</span><span class="sxs-lookup"><span data-stu-id="c15ac-175">Comments</span></span>  
  
-   <span data-ttu-id="c15ac-176">如果队列正在动态创建，但未删除，则将导致错误下, 一个业务流程实例激活时。</span><span class="sxs-lookup"><span data-stu-id="c15ac-176">If the queue is being dynamically created, but not deleted, it will result in errors when the next orchestration instance is activated.</span></span>  
  
-   <span data-ttu-id="c15ac-177">还有其他方法动态; 设置 URI此示例指定一个选项。</span><span class="sxs-lookup"><span data-stu-id="c15ac-177">There are other ways to set the URI dynamically; this sample specifies just one option.</span></span> <span data-ttu-id="c15ac-178">例如，可以通过读取某些属性在消息上下文中的设置 URI。</span><span class="sxs-lookup"><span data-stu-id="c15ac-178">For example, the URI could be set by reading some property in the message context.</span></span>  
  
-   <span data-ttu-id="c15ac-179">如果没有满足匹配选项在队列中的没有消息，则返回一个虚拟消息。</span><span class="sxs-lookup"><span data-stu-id="c15ac-179">If there are no messages in the queue that satisfy the match options, a dummy message is returned.</span></span>  
  
-   <span data-ttu-id="c15ac-180">由于此示例使用动态发送端口，可能需要指定重试和事务等其他选项。</span><span class="sxs-lookup"><span data-stu-id="c15ac-180">Because this sample uses dynamic send ports, other options may need to be specified, such as retry and transactions.</span></span> <span data-ttu-id="c15ac-181">由适配器公开的上下文属性用于将消息发送到动态要求响应端口前设置这些选项。</span><span class="sxs-lookup"><span data-stu-id="c15ac-181">Use the context properties exposed by the adapter to set these options before sending the message out to the dynamic solicit-response port.</span></span>  
  
-   <span data-ttu-id="c15ac-182">可以创建和使用动态删除 MQSeries 队列**MQSAdapterAdmin2**接口。</span><span class="sxs-lookup"><span data-stu-id="c15ac-182">MQSeries queues can be created and deleted dynamically by using the **MQSAdapterAdmin2** interface.</span></span> <span data-ttu-id="c15ac-183">如何动态创建 MQSeries 队列的示例，请参阅"支持的队列管理"在[ http://go.microsoft.com/fwlink/?LinkId=89400 ](http://go.microsoft.com/fwlink/?LinkId=89400)。</span><span class="sxs-lookup"><span data-stu-id="c15ac-183">For an example of how to dynamically create MQSeries queues, see "Support for Queue Management" at [http://go.microsoft.com/fwlink/?LinkId=89400](http://go.microsoft.com/fwlink/?LinkId=89400).</span></span>