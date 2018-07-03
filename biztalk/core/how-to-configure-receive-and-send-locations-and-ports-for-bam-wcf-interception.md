---
title: 如何配置接收和发送位置及端口用于 BAM WCF 侦听 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 501194dc-427a-4910-88c9-19cf47daeaad
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d6fb5a58efe721f3000dddefb0354bd7834d46c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991646"
---
# <a name="how-to-configure-receive-and-send-locations-and-ports-for-bam-wcf-interception"></a><span data-ttu-id="cb8ce-102">如何配置 BAM WCF 侦听的接收和发送位置及端口</span><span class="sxs-lookup"><span data-stu-id="cb8ce-102">How to Configure Receive and Send Locations and Ports for BAM WCF Interception</span></span>
<span data-ttu-id="cb8ce-103">在此过程中，您可以在基于内容的路由 (CBR) 方案中配置接收和发送位置，以便直接演示关键概念。</span><span class="sxs-lookup"><span data-stu-id="cb8ce-103">In this procedure you configure the receive and send locations in a content-based routing (CBR) scenario in order to demonstrate the key concepts in a straightforward manner.</span></span> <span data-ttu-id="cb8ce-104">在此演示的概念可适用于作为 [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] 服务公开的业务流程。</span><span class="sxs-lookup"><span data-stu-id="cb8ce-104">The concepts demonstrated here can be applied to an orchestration that is exposed as a [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] service.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="cb8ce-105">必要條件</span><span class="sxs-lookup"><span data-stu-id="cb8ce-105">Prerequisites</span></span>  
 <span data-ttu-id="cb8ce-106">此过程假定您已执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="cb8ce-106">This procedure assumes that you have:</span></span>  

-   <span data-ttu-id="cb8ce-107">修改 machince.config 文件，如中所示[如何将 BAM 侦听器行为添加到 Machine.config 文件](../core/how-to-add-the-bam-interceptor-behavior-to-the-machine-config-file.md)。</span><span class="sxs-lookup"><span data-stu-id="cb8ce-107">Modified your machince.config file as shown in [How to Add the BAM Interceptor Behavior to the Machine.config File](../core/how-to-add-the-bam-interceptor-behavior-to-the-machine-config-file.md).</span></span>  

-   <span data-ttu-id="cb8ce-108">创建 WCF 适配器的 BizTalk Server 中所示[如何创建用于 BizTalk Server 的 WCF 适配器](../core/how-to-create-a-wcf-adapter-for-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="cb8ce-108">Created a WCF adapter for BizTalk Server as show in [How to Create a WCF Adapter for BizTalk Server](../core/how-to-create-a-wcf-adapter-for-biztalk-server.md).</span></span>  

### <a name="to-configure-the-receive-and-send-locations"></a><span data-ttu-id="cb8ce-109">配置接收和发送位置</span><span class="sxs-lookup"><span data-stu-id="cb8ce-109">To configure the receive and send locations</span></span>  

1. <span data-ttu-id="cb8ce-110">打开 BizTalk 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="cb8ce-110">Open the BizTalk Administration Console.</span></span> <span data-ttu-id="cb8ce-111">若要执行此操作，请单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="cb8ce-111">To do this, click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="cb8ce-112">展开控制台树以找到 BizTalk 应用程序的“接收位置”节点。</span><span class="sxs-lookup"><span data-stu-id="cb8ce-112">Expand the console tree to locate the Receive Locations node for your BizTalk application.</span></span> <span data-ttu-id="cb8ce-113">单击[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，单击**应用程序**，单击应用程序中所选[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务类型对话框的，然后单击**接收位置**。</span><span class="sxs-lookup"><span data-stu-id="cb8ce-113">Click [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], click **Applications**, click the application you selected in the [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] Service Type dialog box, and then click **Receive Locations**.</span></span> <span data-ttu-id="cb8ce-114">这将生成一个与所创建位置相对应的新接收位置。</span><span class="sxs-lookup"><span data-stu-id="cb8ce-114">There will be a new receive location corresponding to the one you created.</span></span> <span data-ttu-id="cb8ce-115">但该位置将处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="cb8ce-115">It will be in disabled status.</span></span>  

3. <span data-ttu-id="cb8ce-116">双击接收位置以打开**接收位置属性**对话框框中，，然后选择 Wcf-custom 作为传输类型。</span><span class="sxs-lookup"><span data-stu-id="cb8ce-116">Double-click the receive location to open the **Receive Location Properties** dialog box, and then choose WCF-Custom as the transport type.</span></span>  

4. <span data-ttu-id="cb8ce-117">单击**配置**按钮以打开**Wcf-custom 传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="cb8ce-117">Click the **Configure** button to open the **WCF-Custom Transport Properties** dialog box.</span></span>  

5. <span data-ttu-id="cb8ce-118">单击**绑定**选项卡并选择你想要使用的绑定。</span><span class="sxs-lookup"><span data-stu-id="cb8ce-118">Click the **Binding** tab and select the binding you want to use.</span></span>  

6. <span data-ttu-id="cb8ce-119">单击**行为**选项卡上，右键单击**EndpointBehavior**节点，并选择**添加扩展**。</span><span class="sxs-lookup"><span data-stu-id="cb8ce-119">Click the **Behavior** tab, right-click the **EndpointBehavior** node, and then select **Add Extension**.</span></span>  

7. <span data-ttu-id="cb8ce-120">选择的 BAMEndPointExtension （这是添加到 machine.config 文件的扩展名），然后依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="cb8ce-120">Select the BAMEndPointExtension (this is the extension you added to the machine.config file), and then click **Ok**.</span></span>  

    <span data-ttu-id="cb8ce-121">![选择行为扩展屏幕](../core/media/fe830d29-504e-465a-9316-b3f0db2dbc24.gif "fe830d29-504e-465a-9316-b3f0db2dbc24")</span><span class="sxs-lookup"><span data-stu-id="cb8ce-121">![Select Behavior Extension screen](../core/media/fe830d29-504e-465a-9316-b3f0db2dbc24.gif "fe830d29-504e-465a-9316-b3f0db2dbc24")</span></span>  

8. <span data-ttu-id="cb8ce-122">选择刚创建的扩展，输入以下值，然后单击**确定**:</span><span class="sxs-lookup"><span data-stu-id="cb8ce-122">Select the extension you just created, enter the following values, and then click **OK**:</span></span>  


   |      <span data-ttu-id="cb8ce-123">“属性”</span><span class="sxs-lookup"><span data-stu-id="cb8ce-123">Property</span></span>      |                                                        <span data-ttu-id="cb8ce-124">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="cb8ce-124">Value</span></span>                                                         |
   |--------------------|----------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="cb8ce-125">PollingIntervalSec</span><span class="sxs-lookup"><span data-stu-id="cb8ce-125">PollingIntervalSec</span></span> |                                                          <span data-ttu-id="cb8ce-126">10</span><span class="sxs-lookup"><span data-stu-id="cb8ce-126">10</span></span>                                                          |
   |  <span data-ttu-id="cb8ce-127">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="cb8ce-127">ConnectionString</span></span>  | <span data-ttu-id="cb8ce-128">ConnectionString： 集成安全性 = SSPI;持久性安全信息 = False; Initial Catalog = BAMPrimaryImport; 数据源 =</span><span class="sxs-lookup"><span data-stu-id="cb8ce-128">ConnectionString: Integrated Security=SSPI;Persist Security Info=False;Initial Catalog=BAMPrimaryImport;Data Source=</span></span> |


9. <span data-ttu-id="cb8ce-129">在中**接收位置属性**对话框中，选择**PassThruReceive**从**接收管道**下拉列表中，并单击**确定**.</span><span class="sxs-lookup"><span data-stu-id="cb8ce-129">In the **Receive Location Properties** dialog box, select **PassThruReceive** from the **Receive pipeline** drop-down list, and then click **OK**.</span></span>  

10. <span data-ttu-id="cb8ce-130">启用该接收位置并刷新管理控制台。</span><span class="sxs-lookup"><span data-stu-id="cb8ce-130">Enable the receive location and refresh the Administration console.</span></span> <span data-ttu-id="cb8ce-131">已启动状态表示设置成功。</span><span class="sxs-lookup"><span data-stu-id="cb8ce-131">A started status indicates that the setup is successful.</span></span>  

## <a name="see-also"></a><span data-ttu-id="cb8ce-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="cb8ce-132">See Also</span></span>  
 [<span data-ttu-id="cb8ce-133">配置 WCF 适配器以侦听 BAM 数据</span><span class="sxs-lookup"><span data-stu-id="cb8ce-133">Configuring the WCF Adapter to Intercept BAM Data</span></span>](../core/configuring-the-wcf-adapter-to-intercept-bam-data.md)