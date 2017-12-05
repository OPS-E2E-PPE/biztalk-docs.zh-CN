---
title: "部署和测试应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e2c86d5f-1849-4b7d-8061-23f156245f5b
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d93284823c2ce5d0c00a1601a5b9ae0aac4643c
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="deploy-and-test-the-application"></a><span data-ttu-id="1abfb-102">部署并测试应用程序</span><span class="sxs-lookup"><span data-stu-id="1abfb-102">Deploy and test the application</span></span>
> [!NOTE]
>  <span data-ttu-id="1abfb-103">本教程仅适用于 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="1abfb-103">This tutorial applies to BizTalk Server only.</span></span>  
  
 <span data-ttu-id="1abfb-104">在本主题中，我们将生成、部署、配置并测试 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序。</span><span class="sxs-lookup"><span data-stu-id="1abfb-104">In this topic, we build, deploy, configure, and test the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application.</span></span>  
  
## <a name="build-and-deploy-the-application"></a><span data-ttu-id="1abfb-105">生成并部署应用程序</span><span class="sxs-lookup"><span data-stu-id="1abfb-105">Build and deploy the application</span></span>  
  
1.  <span data-ttu-id="1abfb-106">在解决方案资源管理器，右键单击 BizTalk 项目名称，，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="1abfb-106">In the Solution Explorer, right-click the BizTalk project name, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="1abfb-107">在“属性”页上，单击“签名”选项卡，选中“为程序集签名”复选框，然后从下拉菜单中选择新建一个强名称密钥文件的选项。</span><span class="sxs-lookup"><span data-stu-id="1abfb-107">On the Property page, click the Signing tab, select the Sign the assembly check box, and from the drop-down choose the option to create a new strong name key file.</span></span> <span data-ttu-id="1abfb-108">按照提示创建此文件。</span><span class="sxs-lookup"><span data-stu-id="1abfb-108">Follow the prompts to create the file.</span></span>  
  
3.  <span data-ttu-id="1abfb-109">保存对项目所做的更改。</span><span class="sxs-lookup"><span data-stu-id="1abfb-109">Save changes to the project.</span></span> <span data-ttu-id="1abfb-110">在解决方案资源管理器，右键单击解决方案名称，然后单击**生成解决方案**。</span><span class="sxs-lookup"><span data-stu-id="1abfb-110">In Solution Explorer, right-click the solution name, and then click **Build Solution**.</span></span>  
  
4.  <span data-ttu-id="1abfb-111">成功生成项目后，在解决方案资源管理器，右键单击解决方案名称，然后单击**部署解决方案**。</span><span class="sxs-lookup"><span data-stu-id="1abfb-111">After project builds successfully, in the Solution Explorer, right-click the solution name, and then click **Deploy Solution**.</span></span>  
  
## <a name="configure-the-application"></a><span data-ttu-id="1abfb-112">配置应用程序</span><span class="sxs-lookup"><span data-stu-id="1abfb-112">Configure the application</span></span>  
 <span data-ttu-id="1abfb-113">若要配置该应用程序，请在 [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]中创建发送和接收端口，然后将这些端口绑定到业务流程以及作为业务流程的一部分而创建的逻辑发送/接收端口。</span><span class="sxs-lookup"><span data-stu-id="1abfb-113">To configure the application, in [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], create the send and receive ports and then bind them to the orchestration and the logical send/receive ports created as part of the orchestration.</span></span>  
  
1.  <span data-ttu-id="1abfb-114">创建 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序用来接收 JSON 采购订单的接收端口。</span><span class="sxs-lookup"><span data-stu-id="1abfb-114">Create a receive port through which a JSON purchase order is received by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application.</span></span>  
  
    1.  <span data-ttu-id="1abfb-115">在[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 应用程序 1**，右键单击**接收端口**，指向**新建**，然后单击**单向接收端口**.</span><span class="sxs-lookup"><span data-stu-id="1abfb-115">In [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Application 1**, right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
    2.  <span data-ttu-id="1abfb-116">提供接收端口的名称，然后从左侧的平移中，单击**接收位置**。</span><span class="sxs-lookup"><span data-stu-id="1abfb-116">Provide a name for the receive port, and then from the left pan, click **Receive Locations**.</span></span> <span data-ttu-id="1abfb-117">在**接收位置**选项卡上，单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="1abfb-117">In the **Receive Locations** tab, click **New**.</span></span>  
  
    3.  <span data-ttu-id="1abfb-118">指定接收位置的名称，请选择与具有端口类型**文件**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="1abfb-118">Specify a name for the receive location, select the port type as **FILE**, and then click **Configure**.</span></span>  
  
    4.  <span data-ttu-id="1abfb-119">提供接收位置将从中选取传入 JSON 采购订单的文件夹位置。</span><span class="sxs-lookup"><span data-stu-id="1abfb-119">Provide the folder location from where the receive location will pick the incoming JSON purchase order.</span></span> <span data-ttu-id="1abfb-120">指定`*.json`作为文件掩码，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="1abfb-120">Specify `*.json` as the file mask and then click **OK**.</span></span>  
  
    5.  <span data-ttu-id="1abfb-121">从**接收管道**下拉列表中，选择**JSONToXml**。</span><span class="sxs-lookup"><span data-stu-id="1abfb-121">From the **Receive Pipeline** drop-down, select **JSONToXml**.</span></span> <span data-ttu-id="1abfb-122">此时，你已在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序中创建此自定义接收管道。</span><span class="sxs-lookup"><span data-stu-id="1abfb-122">You created this custom receive pipeline in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application.</span></span> <span data-ttu-id="1abfb-123">右键单击省略号**（...）**按钮旁边向管道，然后在下**阶段 1 – Deocde 组件**，提供以下值：</span><span class="sxs-lookup"><span data-stu-id="1abfb-123">Right-click the ellipsis **(…)** button next to the pipeline, and then under **Stage 1 – Deocde Component**, provide the following values:</span></span>  
  
        -   <span data-ttu-id="1abfb-124">RootNode-`ROOT`</span><span class="sxs-lookup"><span data-stu-id="1abfb-124">RootNode - `ROOT`</span></span>  
  
        -   <span data-ttu-id="1abfb-125">RootNodeNamespace –`http://BTSJSON`。</span><span class="sxs-lookup"><span data-stu-id="1abfb-125">RootNodeNamespace –`http://BTSJSON`.</span></span>  
  
         <span data-ttu-id="1abfb-126">这些值代表使用 JSON 架构向导从 JSON 采购订单生成的 XML 采购订单架构的目标命名空间和根节点名。</span><span class="sxs-lookup"><span data-stu-id="1abfb-126">These values represent the target namespace and the root node name of the XML purchase order schema that was generated from the JSON purchase order using the JSON schema wizard.</span></span>  
  
    6.  <span data-ttu-id="1abfb-127">单击**确定**直到退出所有打开的对话框。</span><span class="sxs-lookup"><span data-stu-id="1abfb-127">Click **OK** until you exit all open dialog boxes.</span></span>  
  
2.  <span data-ttu-id="1abfb-128">创建用于向外发送 JSON 发票消息的发送端口。</span><span class="sxs-lookup"><span data-stu-id="1abfb-128">Create a send port for sending out JSON invoice messages.</span></span>  
  
    1.  <span data-ttu-id="1abfb-129">在[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 应用程序 1**，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**.</span><span class="sxs-lookup"><span data-stu-id="1abfb-129">In [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Application 1**, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
    2.  <span data-ttu-id="1abfb-130">指定发送端口的名称，请选择与具有端口类型**文件**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="1abfb-130">Specify a name for the send port, select the port type as **FILE**, and then click **Configure**.</span></span>  
  
    3.  <span data-ttu-id="1abfb-131">提供发送端口将传出 JSON 发票复制到的文件夹位置。</span><span class="sxs-lookup"><span data-stu-id="1abfb-131">Provide the folder location where the send port copies the outgoing JSON invoice.</span></span> <span data-ttu-id="1abfb-132">指定`%MessageID%.json`作为文件名称，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="1abfb-132">Specify `%MessageID%.json` as the file name and then click **OK**.</span></span>  
  
    4.  <span data-ttu-id="1abfb-133">从**发送管道**下拉列表中，选择**XmlToJSON**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="1abfb-133">From the **Send Pipeline** drop-down, select **XmlToJSON**, and then click **OK**.</span></span>  
  
    5.  <span data-ttu-id="1abfb-134">单击**确定**直到退出所有打开的对话框。</span><span class="sxs-lookup"><span data-stu-id="1abfb-134">Click **OK** until you exit all open dialog boxes.</span></span>  
  
3.  <span data-ttu-id="1abfb-135">最后，将作为业务流程一部分创建的逻辑端口绑定到你当前已创建的物理端口，以对应用程序进行配置。</span><span class="sxs-lookup"><span data-stu-id="1abfb-135">Finally, bind the logical ports you created as part of the orchestration to the physical ports you created now to configure the application.</span></span>  
  
    1.  <span data-ttu-id="1abfb-136">右键单击**BizTalk 应用程序 1**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="1abfb-136">Right-click **BizTalk Application 1**, and then click **Configure**.</span></span>  
  
    2.  <span data-ttu-id="1abfb-137">从左窗格中，单击**ProcessPO**。</span><span class="sxs-lookup"><span data-stu-id="1abfb-137">From the left pane, click **ProcessPO**.</span></span> <span data-ttu-id="1abfb-138">从右窗格中，将相关联[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]主机，将逻辑端口映射到的物理端口，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="1abfb-138">From the right pane, associate a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] host, map the logical ports to the physical ports, and then click **OK**.</span></span>  
  
    3.  <span data-ttu-id="1abfb-139">右键单击**BizTalk 应用程序 1**，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="1abfb-139">Right-click **BizTalk Application 1**, and then click **Start**.</span></span>  
  
## <a name="test-the-application"></a><span data-ttu-id="1abfb-140">测试应用程序</span><span class="sxs-lookup"><span data-stu-id="1abfb-140">Test the application</span></span>  
  
1.  <span data-ttu-id="1abfb-141">导航到你下载的示例和从**testmessage 存储库库**文件夹中，复制**JsonPurchaseOrder.json**，并将其粘贴在与接收位置关联的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="1abfb-141">Navigate to the sample you downloaded, and from the **TestMessage** folder, copy **JsonPurchaseOrder.json**, and paste it in the folder you associated with the receive location.</span></span> <span data-ttu-id="1abfb-142">等待此文件消失。</span><span class="sxs-lookup"><span data-stu-id="1abfb-142">Wait till the file disappears.</span></span>  
  
2.  <span data-ttu-id="1abfb-143">导航到与你所创建的发送端口关联的文件夹。</span><span class="sxs-lookup"><span data-stu-id="1abfb-143">Navigate to the folder that you associated with the send port you created.</span></span> <span data-ttu-id="1abfb-144">请注意，   ***\<GUID\>*.json**文件位于文件夹中可用。</span><span class="sxs-lookup"><span data-stu-id="1abfb-144">Notice that a ***\<GUID\>*.json** file is available in the folder.</span></span> <span data-ttu-id="1abfb-145">打开此文件并验证它是否是发票消息。</span><span class="sxs-lookup"><span data-stu-id="1abfb-145">Open the file and verify that it’s the invoice message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1abfb-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1abfb-146">See Also</span></span>  
 [<span data-ttu-id="1abfb-147">使用 BizTalk Server 处理 JSON 消息</span><span class="sxs-lookup"><span data-stu-id="1abfb-147">Processing JSON messages using BizTalk Server</span></span>](../core/processing-json-messages-using-biztalk-server.md)