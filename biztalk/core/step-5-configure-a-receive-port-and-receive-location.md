---
title: 步骤 5：配置接收端口和接收位置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 43fc8d12-5fde-4ddf-a7f0-770f078ba66b
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4f4976c585caf858c27680b156ec3d01b09d439
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244351"
---
# <a name="step-5-configure-a-receive-port-and-receive-location"></a><span data-ttu-id="ac351-102">步骤 5：配置接收端口和接收位置</span><span class="sxs-lookup"><span data-stu-id="ac351-102">Step 5: Configure a Receive Port and Receive Location</span></span>
<span data-ttu-id="ac351-103">![步骤 5 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-5of9.gif "Step_5of9")</span><span class="sxs-lookup"><span data-stu-id="ac351-103">![Step 5 of 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-5of9.gif "Step_5of9")</span></span>  
  
 <span data-ttu-id="ac351-104">在此步骤中配置接收端口和接收位置接收 850 消息的 Fabrikam 参与方设置的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="ac351-104">In this step you configure a receive port and receive location for receiving the 850 message in the folder set up for the Fabrikam party.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ac351-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="ac351-105">Prerequisites</span></span>  
 <span data-ttu-id="ac351-106">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。</span><span class="sxs-lookup"><span data-stu-id="ac351-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-configure-a-receive-port-and-receive-location-for-receiving-the-850-message"></a><span data-ttu-id="ac351-107">若要配置接收端口和接收位置以接收 850 消息</span><span class="sxs-lookup"><span data-stu-id="ac351-107">To configure a receive port and receive location for receiving the 850 message</span></span>  
  
1. <span data-ttu-id="ac351-108">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**， **BizTalk 组**，**应用程序**，然后**BizTalk应用程序 1**。</span><span class="sxs-lookup"><span data-stu-id="ac351-108">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand **BizTalk Server Administration**, **BizTalk Group**, **Applications**, and then **BizTalk Application 1**.</span></span> <span data-ttu-id="ac351-109">右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="ac351-109">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
2. <span data-ttu-id="ac351-110">在接收端口属性对话框中，在**名称**字段中，输入`ReceiveEDI_fromTHEM_A`。</span><span class="sxs-lookup"><span data-stu-id="ac351-110">In the Receive Port Properties dialog box, in the **Name** field, enter `ReceiveEDI_fromTHEM_A`.</span></span>  
  
3. <span data-ttu-id="ac351-111">单击**接收位置**在控制台树中，然后单击**新建**右侧窗格中。</span><span class="sxs-lookup"><span data-stu-id="ac351-111">Click **Receive Locations** in the console tree, and then click **New** in the right-hand pane.</span></span>  
  
4. <span data-ttu-id="ac351-112">在中**接收位置属性**对话框中**名称**字段中，输入`fromTHEM_4010_850`。</span><span class="sxs-lookup"><span data-stu-id="ac351-112">In the **Receive Location Properties** dialog box, in the **Name** field, enter `fromTHEM_4010_850`.</span></span>  
  
5. <span data-ttu-id="ac351-113">有关**类型**，选择**文件**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="ac351-113">For **Type**, select **FILE**, and then click **Configure**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ac351-114">由于测试消息是平面文件传送到文件夹，接收位置的传输类型为 FILE。</span><span class="sxs-lookup"><span data-stu-id="ac351-114">The transport type of the receive location is FILE because the test message is a flat file delivered into a folder.</span></span>  
  
6. <span data-ttu-id="ac351-115">在中**FILE 传输属性**对话框中，单击**浏览**按钮旁边**接收文件夹**字段。</span><span class="sxs-lookup"><span data-stu-id="ac351-115">In the **FILE Transport Properties** dialog box, click the **Browse** button next to the **Receive folder** field.</span></span> <span data-ttu-id="ac351-116">在中**浏览文件夹**对话框中，转到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations\Scenario A\fromTHEM，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ac351-116">In the **Browse for Folder** dialog box, move to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations\Scenario A\fromTHEM, and then click **OK**.</span></span>  
  
7. <span data-ttu-id="ac351-117">在中**FILE 传输属性**对话框中，更改**文件掩码**到 **\*.txt**然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ac351-117">In the **FILE Transport Properties** dialog box, change the **File mask** to **\*.txt** and click **OK**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ac351-118">由于输入的测试消息是一个文本文件，SamplePO.txt 文件掩码设置为 \*.txt。</span><span class="sxs-lookup"><span data-stu-id="ac351-118">The file mask is set to \*.txt because the input test message is a text file, SamplePO.txt.</span></span>  
  
8. <span data-ttu-id="ac351-119">在中**接收位置属性**对话框中**接收管道**字段中，选择**EdiReceive**。</span><span class="sxs-lookup"><span data-stu-id="ac351-119">In the **Receive Location Properties** dialog box, in the **Receive Pipeline** field, select **EdiReceive**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ac351-120">接收管道用于接收 EDI 交换，除通过 AS2 传输传递的之外是 EdiReceive 管道。</span><span class="sxs-lookup"><span data-stu-id="ac351-120">The receive pipeline used to receive EDI interchanges, except for those delivered over the AS2 transport, is the EdiReceive pipeline.</span></span> <span data-ttu-id="ac351-121">(AS2EdiReceive 接收管道用于接收通过 AS2 传输 EDI 交换。)</span><span class="sxs-lookup"><span data-stu-id="ac351-121">(The AS2EdiReceive receive pipeline is used to receive EDI interchanges delivered over the AS2 transport.)</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ac351-122">如果 EdiReceive 接收管道的下拉列表中未列出，应用程序可能不具有对 BizTalk EDI 应用程序的引用。</span><span class="sxs-lookup"><span data-stu-id="ac351-122">If EdiReceive is not listed in the drop-down list for receive pipeline, your application may not have a reference to the BizTalk EDI Application.</span></span> <span data-ttu-id="ac351-123">若要添加引用，请参阅[如何添加对 BizTalk Server EDI 应用程序的引用](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)。</span><span class="sxs-lookup"><span data-stu-id="ac351-123">To add the reference, see [How to Add a Reference to the BizTalk Server EDI Application](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).</span></span>  
  
9. <span data-ttu-id="ac351-124">单击**确定**，然后单击**确定**试。</span><span class="sxs-lookup"><span data-stu-id="ac351-124">Click **OK**, and then click **OK** again.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ac351-125">此外应为具有 BizTalk 服务登录权限的帐户授予与 fromTHEM_4010_850 接收位置关联的接收文件夹的完全访问权限 ([!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\ProcessEDI_TestLocations\fromTHEM)。</span><span class="sxs-lookup"><span data-stu-id="ac351-125">The account that has log-on privileges for the BizTalk service should also be granted full access permissions for the receive folder associated with the fromTHEM_4010_850 receive location ([!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\ProcessEDI_TestLocations\fromTHEM).</span></span> <span data-ttu-id="ac351-126">如果没有，请尝试启用接收位置时，将收到错误。</span><span class="sxs-lookup"><span data-stu-id="ac351-126">If not, you will receive an error when attempting to enable the receive location.</span></span> <span data-ttu-id="ac351-127">若要更改接收文件夹的访问权限，请转到在中的安全选项卡**属性**对话框中，在 Windows 资源管理器中该文件夹。</span><span class="sxs-lookup"><span data-stu-id="ac351-127">To change the access permissions for the receive folder, go to the Security tab in the **Properties** dialog box for that folder in Windows Explorer.</span></span>  
  
10. <span data-ttu-id="ac351-128">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**接收位置**，右键单击**fromTHEM_4010_850**，然后单击**启用**。</span><span class="sxs-lookup"><span data-stu-id="ac351-128">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, click **Receive Locations**, right-click **fromTHEM_4010_850**, and then click **Enable**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="ac351-129">后续步骤</span><span class="sxs-lookup"><span data-stu-id="ac351-129">Next Steps</span></span>  
 <span data-ttu-id="ac351-130">配置发送端口 (**toOrderSystem**) 以将 850 消息发送到 OrderSystem，如中所述[步骤 6:配置发送端口以将数据发送到你的组织](../core/step-6-configure-a-send-port-to-send-data-to-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="ac351-130">You configure the send port (**toOrderSystem**) to send the 850 message to OrderSystem, as described in [Step 6: Configure a Send Port to Send Data to Your Organization](../core/step-6-configure-a-send-port-to-send-data-to-your-organization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac351-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="ac351-131">See Also</span></span>  
 [<span data-ttu-id="ac351-132">配置接收 EDI 消息和确认的端口</span><span class="sxs-lookup"><span data-stu-id="ac351-132">Configuring a Port to Receive EDI Messages and Acknowledgments</span></span>](../core/configuring-a-port-to-receive-edi-messages-and-acknowledgments.md)