---
title: 使用事件中心适配器 |Microsoft 文档
description: 发送和接收消息 BizTalk Server 中使用 Azure 事件中心适配器
ms.custom: ''
ms.date: 11/16/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
author: MandiOhlinger
ms.author: plarsen
manager: anneta
ms.openlocfilehash: cb9bbe26f07d87d7cccc084b6842b6d0974fdbb3
ms.sourcegitcommit: 3371ffd8ceca02e2b3715d53a1e0c0a59045912e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/07/2018
ms.locfileid: "34848917"
---
# <a name="event-hub-adapter-in-biztalk"></a><span data-ttu-id="32167-103">BizTalk 中的事件中心适配器</span><span class="sxs-lookup"><span data-stu-id="32167-103">Event Hub adapter in BizTalk</span></span>

## <a name="overview"></a><span data-ttu-id="32167-104">概述</span><span class="sxs-lookup"><span data-stu-id="32167-104">Overview</span></span>
<span data-ttu-id="32167-105">**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]功能包 2**，可以发送和接收 BizTalk Server 和 Azure 事件中心之间的消息。</span><span class="sxs-lookup"><span data-stu-id="32167-105">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] Feature Pack 2**, you can send and receive messages between BizTalk Server and Azure Event Hubs.</span></span> 

<span data-ttu-id="32167-106">Azure 事件中心是高度可伸缩的数据流平台，并可以接收和处理数百万个每秒的事件。</span><span class="sxs-lookup"><span data-stu-id="32167-106">Azure Event Hubs is a highly scalable data streaming platform, and can receive and process millions of events per second.</span></span> <span data-ttu-id="32167-107">[什么是事件中心？](https://docs.microsoft.com/azure/event-hubs/event-hubs-what-is-event-hubs)提供更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="32167-107">[What is Event Hubs?](https://docs.microsoft.com/azure/event-hubs/event-hubs-what-is-event-hubs) provides more details.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="32167-108">必要條件</span><span class="sxs-lookup"><span data-stu-id="32167-108">Prerequisites</span></span>

* <span data-ttu-id="32167-109">创建[Azure 事件中心命名空间和事件中心](https://docs.microsoft.com/azure/event-hubs/event-hubs-create)</span><span class="sxs-lookup"><span data-stu-id="32167-109">Create an [Azure event hubs namespace and event hub](https://docs.microsoft.com/azure/event-hubs/event-hubs-create)</span></span>
* <span data-ttu-id="32167-110">创建[与容器的 Azure blob 存储帐户](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account)</span><span class="sxs-lookup"><span data-stu-id="32167-110">Create an [Azure blob storage account with a container](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account)</span></span>
* <span data-ttu-id="32167-111">安装[功能包 2](https://aka.ms/bts2016fp2) BizTalk 服务器上</span><span class="sxs-lookup"><span data-stu-id="32167-111">Install [Feature Pack 2](https://aka.ms/bts2016fp2) on your BizTalk Server</span></span>

<span data-ttu-id="32167-112">现在创建事件中心，并且你有连接字符串需要发送和接收事件。</span><span class="sxs-lookup"><span data-stu-id="32167-112">Your event hub is now created, and you have the connection strings you need to send and receive events.</span></span>

## <a name="send-messages-to-event-hubs"></a><span data-ttu-id="32167-113">将消息发送到事件中心</span><span class="sxs-lookup"><span data-stu-id="32167-113">Send messages to Event Hubs</span></span>

1.  <span data-ttu-id="32167-114">在 BizTalk Server 管理控制台中，右键单击**发送端口**，选择**新建**，然后选择**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="32167-114">In the BizTalk Server Administration console, right-click **Send Ports**, select **New**, and select **Static One-way send port**.</span></span>

    <span data-ttu-id="32167-115">[创建发送端口](../core/how-to-create-a-send-port2.md)提供了一些指导。</span><span class="sxs-lookup"><span data-stu-id="32167-115">[Create a Send Port](../core/how-to-create-a-send-port2.md) provides some guidance.</span></span>

2. <span data-ttu-id="32167-116">输入**名称**。</span><span class="sxs-lookup"><span data-stu-id="32167-116">Enter a **Name**.</span></span> <span data-ttu-id="32167-117">在**传输**，将其设置**类型**到**EventHub**，然后选择**配置**。</span><span class="sxs-lookup"><span data-stu-id="32167-117">In **Transport**, set the **Type** to **EventHub**, and select **Configure**.</span></span> 

3. <span data-ttu-id="32167-118">配置**Azure 帐户**属性：</span><span class="sxs-lookup"><span data-stu-id="32167-118">Configure the **Azure Account** properties:</span></span> 

    |<span data-ttu-id="32167-119">使用此选项</span><span class="sxs-lookup"><span data-stu-id="32167-119">Use this</span></span>|<span data-ttu-id="32167-120">执行的操作</span><span class="sxs-lookup"><span data-stu-id="32167-120">To do this</span></span>|  
    |---|---|  
    | <span data-ttu-id="32167-121">**登录**</span><span class="sxs-lookup"><span data-stu-id="32167-121">**Sign-in**</span></span> | <span data-ttu-id="32167-122">登录到你的 Azure 帐户</span><span class="sxs-lookup"><span data-stu-id="32167-122">Sign into your Azure account</span></span> |
    | <span data-ttu-id="32167-123">**订阅**</span><span class="sxs-lookup"><span data-stu-id="32167-123">**Subscription**</span></span> | <span data-ttu-id="32167-124">选择具有 EventHubs 命名空间的订阅</span><span class="sxs-lookup"><span data-stu-id="32167-124">Select the subscription that has your EventHubs namespace</span></span> |
    | <span data-ttu-id="32167-125">**资源组**</span><span class="sxs-lookup"><span data-stu-id="32167-125">**Resource Group**</span></span> | <span data-ttu-id="32167-126">选择你具有 EventHubs 命名空间的资源组</span><span class="sxs-lookup"><span data-stu-id="32167-126">Select your resource group that has your EventHubs namespace</span></span> |

4. <span data-ttu-id="32167-127">配置**终结点**属性：</span><span class="sxs-lookup"><span data-stu-id="32167-127">Configure the **Endpoint** properties:</span></span> 

    |<span data-ttu-id="32167-128">使用此选项</span><span class="sxs-lookup"><span data-stu-id="32167-128">Use this</span></span>|<span data-ttu-id="32167-129">执行的操作</span><span class="sxs-lookup"><span data-stu-id="32167-129">To do this</span></span>|  
    |---|---|  
    | <span data-ttu-id="32167-130">**Namespace**</span><span class="sxs-lookup"><span data-stu-id="32167-130">**Namespace**</span></span> | <span data-ttu-id="32167-131">选择事件中心命名空间，这是类似于 sb: / /*youreventhubnamespace*.servicebus.windows.net/</span><span class="sxs-lookup"><span data-stu-id="32167-131">Select your Event Hubs namespace, which is something like sb://*youreventhubnamespace*.servicebus.windows.net/</span></span> |
    | <span data-ttu-id="32167-132">**名称**</span><span class="sxs-lookup"><span data-stu-id="32167-132">**Name**</span></span> | <span data-ttu-id="32167-133">选择你的事件中心名称 （这在你的事件中心命名空间内创建）</span><span class="sxs-lookup"><span data-stu-id="32167-133">Select the name of your Event Hub (which was created within your Event Hubs namespace)</span></span> |
    | <span data-ttu-id="32167-134">**默认分区键**</span><span class="sxs-lookup"><span data-stu-id="32167-134">**Default Partition Key**</span></span> | <span data-ttu-id="32167-135">可选。</span><span class="sxs-lookup"><span data-stu-id="32167-135">Optional.</span></span> <span data-ttu-id="32167-136">[事件中心编程指南](https://docs.microsoft.com/azure/event-hubs/event-hubs-programming-guide)对此项提供更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="32167-136">[Event Hubs programming guide](https://docs.microsoft.com/azure/event-hubs/event-hubs-programming-guide) provides more details on this key.</span></span> |
    | <span data-ttu-id="32167-137">**身份验证**</span><span class="sxs-lookup"><span data-stu-id="32167-137">**Authentication**</span></span> | <span data-ttu-id="32167-138">**Namespace 访问签名**是默认设置，并自动使用你创建事件中心命名空间时，创建 RootManageSharedAccessKey。</span><span class="sxs-lookup"><span data-stu-id="32167-138">**Namespace Access Signature** is the default, and automatically uses the RootManageSharedAccessKey that's created when you create an Event Hubs namespace.</span></span><br/><br/><span data-ttu-id="32167-139">**实体访问签名**是可以在事件中心的级别 （不是事件中心命名空间的级别） 创建的 SAS 策略。</span><span class="sxs-lookup"><span data-stu-id="32167-139">**Entity Access Signature** is the SAS policy you can create at the Event Hub-level (not the Event Hubs namespace-level).</span></span> <br/><br/><span data-ttu-id="32167-140">[事件中心功能概述](https://docs.microsoft.com/azure/event-hubs/event-hubs-features)说明的详细信息。</span><span class="sxs-lookup"><span data-stu-id="32167-140">[Event Hubs features overview](https://docs.microsoft.com/azure/event-hubs/event-hubs-features) explains more.</span></span> |

    <span data-ttu-id="32167-141">完成后，你的属性类似于以下：</span><span class="sxs-lookup"><span data-stu-id="32167-141">When finished, your properties look similar to the following:</span></span> 

    ![终结点属性](../core/media/event-hub-endpoint-properties.png)


5. <span data-ttu-id="32167-143">可选。</span><span class="sxs-lookup"><span data-stu-id="32167-143">Optional.</span></span> <span data-ttu-id="32167-144">配置**消息**属性。</span><span class="sxs-lookup"><span data-stu-id="32167-144">Configure the **Message** properties.</span></span> <span data-ttu-id="32167-145">**用户定义的消息属性的 Namespace**值表示 BizTalk 消息架构映射到事件中心消息属性。</span><span class="sxs-lookup"><span data-stu-id="32167-145">The **Namespace for User Defined Message Properties** value represents a BizTalk message schema mapped to Event Hubs message properties.</span></span>

6. <span data-ttu-id="32167-146">选择**确定**以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="32167-146">Select **Ok** to save your changes.</span></span> 


### <a name="test-your-send-port"></a><span data-ttu-id="32167-147">测试发送端口</span><span class="sxs-lookup"><span data-stu-id="32167-147">Test your send port</span></span>

<span data-ttu-id="32167-148">你可以使用简单文件接收端口和将消息发送到 Azure 事件中心的位置。</span><span class="sxs-lookup"><span data-stu-id="32167-148">You can use a simple File receive port and location to send messages to your Azure Event Hub.</span></span> 

1. <span data-ttu-id="32167-149">创建使用文件适配器接收端口。</span><span class="sxs-lookup"><span data-stu-id="32167-149">Create a receive port using the File adapter.</span></span> <span data-ttu-id="32167-150">在你接收位置，请将设置**接收文件夹**到 \**C:\Temp\In\**，并将文件掩码设置为 **\*.xml**。</span><span class="sxs-lookup"><span data-stu-id="32167-150">Within your receive location,  set the **Receive folder** to \**C:\Temp\In\**, and set the file mask to **\*.xml**.</span></span>
2. <span data-ttu-id="32167-151">在你的事件中心发送端口属性，设置**筛选器**到`BTS.ReceivePortName == FileReceivePort`。</span><span class="sxs-lookup"><span data-stu-id="32167-151">In your Event Hub send port properties, set the **Filters** to `BTS.ReceivePortName == FileReceivePort`.</span></span>
3. <span data-ttu-id="32167-152">将以下内容粘贴到文本编辑器，并将文件作为**EventHubMessage.xml**。</span><span class="sxs-lookup"><span data-stu-id="32167-152">Paste the following into a text editor, and save the file as **EventHubMessage.xml**.</span></span> <span data-ttu-id="32167-153">这是示例消息。</span><span class="sxs-lookup"><span data-stu-id="32167-153">This is your sample message.</span></span> 

    ```xml
    <Data>
      <DataID>DataID_0</DataID>
      <DataDetails>DataDetails_0</DataDetails>
    </Data>
    ```

4. <span data-ttu-id="32167-154">启动文件接收位置和事件中心发送端口。</span><span class="sxs-lookup"><span data-stu-id="32167-154">Start the File receive location and the Event Hub send port.</span></span>
5. <span data-ttu-id="32167-155">复制**EventHubMessage.xml**到接收文件夹的示例消息 (C:\Temp\In\)。</span><span class="sxs-lookup"><span data-stu-id="32167-155">Copy **EventHubMessage.xml** sample message into the receive folder (C:\Temp\In\).</span></span> <span data-ttu-id="32167-156">发送端口将发送到事件中心的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="32167-156">The send port sends the XML file to the event hub.</span></span>

## <a name="receive-messages-from-event-hubs"></a><span data-ttu-id="32167-157">从事件中心接收消息</span><span class="sxs-lookup"><span data-stu-id="32167-157">Receive messages from Event Hubs</span></span>

1. <span data-ttu-id="32167-158">在 BizTalk Server 管理控制台中，右键单击**接收端口**，选择**新建**，然后选择**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="32167-158">In the BizTalk Server Administration console, right-click **Receive Ports**, select **New**, and select **One-Way receive port**.</span></span> 

    <span data-ttu-id="32167-159">[创建接收端口](../core/how-to-create-a-receive-port.md)提供了一些指导。</span><span class="sxs-lookup"><span data-stu-id="32167-159">[Create a receive port](../core/how-to-create-a-receive-port.md) provides some guidance.</span></span>

2. <span data-ttu-id="32167-160">输入一个名称，并选择**接收位置**。</span><span class="sxs-lookup"><span data-stu-id="32167-160">Enter a name, and select **Receive Locations**.</span></span> 

3. <span data-ttu-id="32167-161">选择**新建**，和**名称**接收位置。</span><span class="sxs-lookup"><span data-stu-id="32167-161">Select **New**, and **Name** the receive location.</span></span> <span data-ttu-id="32167-162">在**传输**，选择**EventHub**从**类型**下拉列表，然后选择**配置**。</span><span class="sxs-lookup"><span data-stu-id="32167-162">In **Transport**, select **EventHub** from the **Type** drop-down list, and then select **Configure**.</span></span> 

4. <span data-ttu-id="32167-163">配置**Azure 帐户**属性：</span><span class="sxs-lookup"><span data-stu-id="32167-163">Configure the **Azure Account** properties:</span></span> 

    |<span data-ttu-id="32167-164">使用此选项</span><span class="sxs-lookup"><span data-stu-id="32167-164">Use this</span></span>|<span data-ttu-id="32167-165">执行的操作</span><span class="sxs-lookup"><span data-stu-id="32167-165">To do this</span></span>|  
    |---|---|  
    | <span data-ttu-id="32167-166">**登录**</span><span class="sxs-lookup"><span data-stu-id="32167-166">**Sign-in**</span></span> | <span data-ttu-id="32167-167">登录到你的 Azure 帐户</span><span class="sxs-lookup"><span data-stu-id="32167-167">Sign into your Azure account</span></span> |
    | <span data-ttu-id="32167-168">**订阅**</span><span class="sxs-lookup"><span data-stu-id="32167-168">**Subscription**</span></span> | <span data-ttu-id="32167-169">选择具有 EventHubs 命名空间的订阅</span><span class="sxs-lookup"><span data-stu-id="32167-169">Select the subscription that has your EventHubs namespace</span></span> |
    | <span data-ttu-id="32167-170">**资源组**</span><span class="sxs-lookup"><span data-stu-id="32167-170">**Resource Group**</span></span> | <span data-ttu-id="32167-171">选择你具有 EventHubs 命名空间的资源组</span><span class="sxs-lookup"><span data-stu-id="32167-171">Select your resource group that has your EventHubs namespace</span></span> |

4. <span data-ttu-id="32167-172">配置**终结点**属性：</span><span class="sxs-lookup"><span data-stu-id="32167-172">Configure the **Endpoint** properties:</span></span> 

    |<span data-ttu-id="32167-173">使用此选项</span><span class="sxs-lookup"><span data-stu-id="32167-173">Use this</span></span>|<span data-ttu-id="32167-174">执行的操作</span><span class="sxs-lookup"><span data-stu-id="32167-174">To do this</span></span>|  
    |---|---|  
    | <span data-ttu-id="32167-175">**Namespace**</span><span class="sxs-lookup"><span data-stu-id="32167-175">**Namespace**</span></span> | <span data-ttu-id="32167-176">选择事件中心命名空间，这是类似于 sb: / /*youreventhubnamespace*.servicebus.windows.net/</span><span class="sxs-lookup"><span data-stu-id="32167-176">Select your Event Hubs namespace, which is something like sb://*youreventhubnamespace*.servicebus.windows.net/</span></span> |
    | <span data-ttu-id="32167-177">**名称**</span><span class="sxs-lookup"><span data-stu-id="32167-177">**Name**</span></span> | <span data-ttu-id="32167-178">选择你的事件中心名称 （这在你的事件中心命名空间内创建）</span><span class="sxs-lookup"><span data-stu-id="32167-178">Select the name of your Event Hub (which was created within your Event Hubs namespace)</span></span> |
    | <span data-ttu-id="32167-179">**使用者组**</span><span class="sxs-lookup"><span data-stu-id="32167-179">**Consumer Group**</span></span> | <span data-ttu-id="32167-180">选择在事件中心内的使用者组。</span><span class="sxs-lookup"><span data-stu-id="32167-180">Select the Consumer group within your Event Hub.</span></span> <span data-ttu-id="32167-181">自动创建默认组。</span><span class="sxs-lookup"><span data-stu-id="32167-181">A default group is created automatically.</span></span> <br/><br/><span data-ttu-id="32167-182">[事件中心功能概述](https://docs.microsoft.com/azure/event-hubs/event-hubs-features)提供更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="32167-182">[Event Hubs features overview](https://docs.microsoft.com/azure/event-hubs/event-hubs-features) provides more details.</span></span> |
    | <span data-ttu-id="32167-183">**身份验证**</span><span class="sxs-lookup"><span data-stu-id="32167-183">**Authentication**</span></span> | <span data-ttu-id="32167-184">**Namespace 访问签名**是默认设置，并自动使用你创建事件中心命名空间时，创建 RootManageSharedAccessKey。</span><span class="sxs-lookup"><span data-stu-id="32167-184">**Namespace Access Signature** is the default, and automatically uses the RootManageSharedAccessKey that's created when you create an Event Hubs namespace.</span></span><br/><br/><span data-ttu-id="32167-185">**实体访问签名**是可以在事件中心的级别 （不是事件中心命名空间的级别） 创建的 SAS 策略。</span><span class="sxs-lookup"><span data-stu-id="32167-185">**Entity Access Signature** is the SAS policy you can create at the Event Hub-level (not the Event Hubs namespace-level).</span></span> <br/><br/><span data-ttu-id="32167-186">[事件中心功能概述](https://docs.microsoft.com/azure/event-hubs/event-hubs-features)说明的详细信息。</span><span class="sxs-lookup"><span data-stu-id="32167-186">[Event Hubs features overview](https://docs.microsoft.com/azure/event-hubs/event-hubs-features) explains more.</span></span> |

    <span data-ttu-id="32167-187">完成后，你的属性类似于以下：</span><span class="sxs-lookup"><span data-stu-id="32167-187">When finished, your properties look similar to the following:</span></span> 

    ![终结点属性](../core/media/event-hub-endpoint-receive-properties.png)

5. <span data-ttu-id="32167-189">配置**检查点**属性。</span><span class="sxs-lookup"><span data-stu-id="32167-189">Configure the **Checkpoint** properties.</span></span> <span data-ttu-id="32167-190">此适配器使用的 Azure blob 存储帐户可靠地读取事件使用检查点，并从中重新启动恢复。</span><span class="sxs-lookup"><span data-stu-id="32167-190">This adapter uses an Azure blob storage account to reliably read events using a checkpoint, and resume from a restart.</span></span> 

    <span data-ttu-id="32167-191">**存储身份验证** </span><span class="sxs-lookup"><span data-stu-id="32167-191">**Storage Authentication** </span></span>  
    <span data-ttu-id="32167-192">选择一个身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="32167-192">Select an authentication method.</span></span> <span data-ttu-id="32167-193">通常情况下，它具有建议使用共享访问签名。</span><span class="sxs-lookup"><span data-stu-id="32167-193">Typically, it's recommended to use a Shared Access Signature.</span></span> <span data-ttu-id="32167-194">以下链接提供了良好的资源来帮助你决定哪种适合你的方案：</span><span class="sxs-lookup"><span data-stu-id="32167-194">The following links are good resources to help you decide which is right for your scenario:</span></span><br/><br/>[<span data-ttu-id="32167-195">有关 Azure 存储帐户</span><span class="sxs-lookup"><span data-stu-id="32167-195">About Azure storage accounts</span></span>](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account)<br/>[<span data-ttu-id="32167-196">使用共享的访问签名 (SAS)</span><span class="sxs-lookup"><span data-stu-id="32167-196">Using shared access signatures (SAS)</span></span>](https://docs.microsoft.com/azure/storage/common/storage-dotnet-shared-access-signature-part-1)

    <span data-ttu-id="32167-197">完成后，你的属性类似于以下：</span><span class="sxs-lookup"><span data-stu-id="32167-197">When finished, your properties look similar to the following:</span></span> 

    ![检查点属性](../core/media/event-hub-receive-checkpoint.png)

6. <span data-ttu-id="32167-199">配置**消息**属性：</span><span class="sxs-lookup"><span data-stu-id="32167-199">Configure the **Message** properties:</span></span> 

    |<span data-ttu-id="32167-200">使用此选项</span><span class="sxs-lookup"><span data-stu-id="32167-200">Use this</span></span>|<span data-ttu-id="32167-201">执行的操作</span><span class="sxs-lookup"><span data-stu-id="32167-201">To do this</span></span>|  
    |---|---|  
    | <span data-ttu-id="32167-202">**Namespace 为用户定义消息属性**</span><span class="sxs-lookup"><span data-stu-id="32167-202">**Namespace for User Defined Message Properties**</span></span> | <span data-ttu-id="32167-203">http://schemas.microsoft.com/BizTalk/EventHubAdapter/EventData/User 是默认架构，但您可以输入另一个架构。</span><span class="sxs-lookup"><span data-stu-id="32167-203">http://schemas.microsoft.com/BizTalk/EventHubAdapter/EventData/User is the default schema, but you can enter another schema.</span></span> <span data-ttu-id="32167-204">此值表示 BizTalk 消息架构映射到事件中心消息属性。</span><span class="sxs-lookup"><span data-stu-id="32167-204">This value represents a BizTalk message schema mapped to Event Hubs message properties.</span></span> |
    | <span data-ttu-id="32167-205">**升级用户定义的属性**</span><span class="sxs-lookup"><span data-stu-id="32167-205">**Promote user defined properties**</span></span> | <span data-ttu-id="32167-206">可选。</span><span class="sxs-lookup"><span data-stu-id="32167-206">Optional.</span></span> <span data-ttu-id="32167-207">如果你愿意，你可以升级这些属性。</span><span class="sxs-lookup"><span data-stu-id="32167-207">You can promote these properties if you prefer.</span></span> <br/><br/><span data-ttu-id="32167-208">**注意**</span><span class="sxs-lookup"><span data-stu-id="32167-208">**NOTE**</span></span><br/><span data-ttu-id="32167-209">需要提升的属性应具有部署的 porperty 架构*之前*接收事件。</span><span class="sxs-lookup"><span data-stu-id="32167-209">The properties that need to be promoted should have a porperty schema deployed *before* receiving events.</span></span>|

7. <span data-ttu-id="32167-210">选择**确定**以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="32167-210">Select **Ok** to save your changes.</span></span> 

### <a name="test-your-receive-settings"></a><span data-ttu-id="32167-211">测试你接收设置</span><span class="sxs-lookup"><span data-stu-id="32167-211">Test your receive settings</span></span>

<span data-ttu-id="32167-212">可以使用简单的文件发送端口从 Azure 事件中心接收消息。</span><span class="sxs-lookup"><span data-stu-id="32167-212">You can use a simple File send port to receive messages from your Azure Event Hub.</span></span> 

1. <span data-ttu-id="32167-213">创建使用文件适配器发送端口。</span><span class="sxs-lookup"><span data-stu-id="32167-213">Create a send port using the File adapter.</span></span> <span data-ttu-id="32167-214">在你发送端口属性内, 设置**目标文件夹**到 **C:\Temp\Out\**，并将设置和**文件名**到 **%MessageID%.xml**.</span><span class="sxs-lookup"><span data-stu-id="32167-214">Within your send port properties, set the **Destination folder** to **C:\Temp\Out\**, and set the and **File name** to **%MessageID%.xml**.</span></span>
2. <span data-ttu-id="32167-215">在你的文件发送端口属性，设置**筛选器**到`BTS.ReceivePortName == EHReceivePort`。</span><span class="sxs-lookup"><span data-stu-id="32167-215">In your File send port properties, set the **Filters** to  `BTS.ReceivePortName == EHReceivePort`.</span></span>
3. <span data-ttu-id="32167-216">开始事件中心接收位置和文件发送端口。</span><span class="sxs-lookup"><span data-stu-id="32167-216">Start the Event Hub receive location and the File send port.</span></span>
4. <span data-ttu-id="32167-217">查找目标文件夹 (c:\temp\out) 中的消息。</span><span class="sxs-lookup"><span data-stu-id="32167-217">Look for messages in the destination folder (c:\temp\out).</span></span>

## <a name="do-more"></a><span data-ttu-id="32167-218">执行更多操作</span><span class="sxs-lookup"><span data-stu-id="32167-218">Do more</span></span>
<span data-ttu-id="32167-219">事件中心被视为"前门"大量其他 Azure 服务，包括 Azure Data Lake、 HD Insight 和的详细信息。</span><span class="sxs-lookup"><span data-stu-id="32167-219">Event Hubs is considered the "front door" to a lot of other Azure services, including Azure Data Lake, HD Insight, and more.</span></span> <span data-ttu-id="32167-220">它旨在处理的消息，并快速进行处理。</span><span class="sxs-lookup"><span data-stu-id="32167-220">It's designed to process a lot of messages, and process them fast.</span></span> <span data-ttu-id="32167-221">有关事件中心和其功能的更多信息：</span><span class="sxs-lookup"><span data-stu-id="32167-221">Read more about Event Hubs, and its features:</span></span> 

[<span data-ttu-id="32167-222">事件中心功能概述</span><span class="sxs-lookup"><span data-stu-id="32167-222">Event Hubs features overview</span></span>](https://docs.microsoft.com/azure/event-hubs/event-hubs-features)  
[<span data-ttu-id="32167-223">什么是事件中心？</span><span class="sxs-lookup"><span data-stu-id="32167-223">What is Event Hubs?</span></span>](https://docs.microsoft.com/azure/event-hubs/event-hubs-what-is-event-hubs)