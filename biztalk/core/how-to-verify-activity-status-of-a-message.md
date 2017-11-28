---
title: "如何验证消息的活动状态 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- activities, verifying status
- PeopleSoft Integration Broker
- verifying message status in PeopleSoft
- messages, verifying status
ms.assetid: b8cee6f9-0f65-4228-a87a-3f3aca6182bf
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 872c1a1fcfcc905caf926c8299f56d49178a8448
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-verify-activity-status-of-a-message"></a><span data-ttu-id="c0eae-102">如何验证消息的活动状态</span><span class="sxs-lookup"><span data-stu-id="c0eae-102">How to Verify Activity Status of a Message</span></span>
<span data-ttu-id="c0eae-103">PeopleSoft 集成 Broker 用于创建 PeopleSoft HTTP 主机和端口 PeopleSoft 发送事件的位置。</span><span class="sxs-lookup"><span data-stu-id="c0eae-103">You use the PeopleSoft Integration Broker to create a PeopleSoft HTTP Host and Port where PeopleSoft sends events.</span></span> <span data-ttu-id="c0eae-104">通过执行以下步骤确保消息处于活动状态并且已被路由。</span><span class="sxs-lookup"><span data-stu-id="c0eae-104">You make sure that the message is active and routed by following these steps.</span></span>  
  
### <a name="to-verify-that-a-message-is-active-and-routed-correctly"></a><span data-ttu-id="c0eae-105">验证消息是否处于活动状态并被正确路由</span><span class="sxs-lookup"><span data-stu-id="c0eae-105">To verify that a Message is active and routed correctly</span></span>  
  
1.  <span data-ttu-id="c0eae-106">单击**启动**，指向**程序**，指向**PeopleSoft 应用程序名称**，然后选择**应用程序设计器**。</span><span class="sxs-lookup"><span data-stu-id="c0eae-106">Click **Start**, point to **Programs**, point to **PeopleSoft Application Name**, and then select **Application Designer**.</span></span>  
  
2.  <span data-ttu-id="c0eae-107">上**PeopleSoft 登录**屏幕中，输入**用户 ID**和**密码**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="c0eae-107">On the **PeopleSoft Sign-on** screen, enter the **User ID** and **Password**, and then click **OK**.</span></span>  
  
     ![](../core/media/psadapter-24-task-userpass.gif "PSAdapter_24_Task_UserPass")  
  
     ![](../core/media/psadapter-25-task-emptydesigner.gif "PSAdapter_25_Task_EmptyDesigner")  
  
3.  <span data-ttu-id="c0eae-108">在应用程序设计器上**文件**菜单上，指向**打开**，然后选择**消息**。</span><span class="sxs-lookup"><span data-stu-id="c0eae-108">In the Application Designer, on the **File** menu, point to **Open**, and then select **Message**.</span></span>  
  
     ![](../core/media/psadapter-26-task-filemessage.gif "PSAdapter_26_Task_FileMessage")  
  
4.  <span data-ttu-id="c0eae-109">在**打开定义**屏幕上，在**名称**字段中，输入`LOCATION_SYNC`，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="c0eae-109">In the **Open Definition** screen, in the **Name** field, enter `LOCATION_SYNC`, and then click **Open**.</span></span>  
  
     ![](../core/media/psadapter-27-task-locationsync.gif "PSAdapter_27_Task_LocationSync")  
  
5.  <span data-ttu-id="c0eae-110">在**定义匹配选择条件**部分中，双击**LOCATION_SYNC**消息以查看属性。</span><span class="sxs-lookup"><span data-stu-id="c0eae-110">In the **Definitions matching selection criteria** section, double-click the **LOCATION_SYNC** message to view the properties.</span></span>  
  
     ![](../core/media/psadapter-28-task-locationproperties.gif "PSAdapter_28_Task_LocationProperties")  
  
6.  <span data-ttu-id="c0eae-111">在应用程序设计器中，右键单击**LOCATION_TBL**，然后选择**消息属性**。</span><span class="sxs-lookup"><span data-stu-id="c0eae-111">In the Application Designer, right-click **LOCATION_TBL**, and select **Message Properties**.</span></span>  
  
     ![](../core/media/psadapter-29-task-loctionmenu.gif "PSAdapter_29_Task_LoctionMenu")  
  
7.  <span data-ttu-id="c0eae-112">上**消息属性**屏幕上，单击**使用**选项卡。</span><span class="sxs-lookup"><span data-stu-id="c0eae-112">On the **Message Properties** screen, click the **Use** tab.</span></span>  
  
     <span data-ttu-id="c0eae-113">验证以下内容，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="c0eae-113">Verify the following, and then click **OK**.</span></span>  
  
    1.  <span data-ttu-id="c0eae-114">**消息：** Active</span><span class="sxs-lookup"><span data-stu-id="c0eae-114">**Message:** Active</span></span>  
  
    2.  <span data-ttu-id="c0eae-115">**Message Channel:** ENTERPRISE_SETUP</span><span class="sxs-lookup"><span data-stu-id="c0eae-115">**Message Channel:** ENTERPRISE_SETUP</span></span>  
  
    3.  <span data-ttu-id="c0eae-116">**默认版本：** VERSION_1</span><span class="sxs-lookup"><span data-stu-id="c0eae-116">**Default Version:** VERSION_1</span></span>  
  
     ![](../core/media/psadapter-30-task-messageuse.gif "PSAdapter_30_Task_MessageUse")  
  
8.  <span data-ttu-id="c0eae-117">退出 Application Designer。</span><span class="sxs-lookup"><span data-stu-id="c0eae-117">Exit the Application Designer.</span></span>  
  
     <span data-ttu-id="c0eae-118">这可确保消息处于活动状态、使用 VERSION_1 并流经 PeopleSoft 中的 ENTERPRISE_SETUP 通道。</span><span class="sxs-lookup"><span data-stu-id="c0eae-118">This makes sure that the Message is in an active state, uses VERSION_1, and flows through the ENTERPRISE_SETUP channel in PeopleSoft.</span></span>  
  
9. <span data-ttu-id="c0eae-119">配置 Integration.Gateway.properties 文件以与 PeopleSoft 应用程序通信。</span><span class="sxs-lookup"><span data-stu-id="c0eae-119">Configure the Integration.Gateway.properties file to communicate with the PeopleSoft application.</span></span>  
  
     <span data-ttu-id="c0eae-120">验证是否设置了以下属性：</span><span class="sxs-lookup"><span data-stu-id="c0eae-120">Verify that the following properties are set:</span></span>  
  
    -   <span data-ttu-id="c0eae-121">**ig.isc.serverurl:** //server:9000</span><span class="sxs-lookup"><span data-stu-id="c0eae-121">**ig.isc.serverurl:** //server:9000</span></span>  
  
    -   <span data-ttu-id="c0eae-122">**ig.isc.userid:** ps 的 ID</span><span class="sxs-lookup"><span data-stu-id="c0eae-122">**ig.isc.userid:** ID for PS</span></span>  
  
    -   <span data-ttu-id="c0eae-123">**ig.isc.password:** ps 的密码</span><span class="sxs-lookup"><span data-stu-id="c0eae-123">**ig.isc.password:** Password for PS</span></span>  
  
    -   <span data-ttu-id="c0eae-124">**ig.isc.toolsrel:**特定版本</span><span class="sxs-lookup"><span data-stu-id="c0eae-124">**ig.isc.toolsrel:** Specific Release</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0eae-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c0eae-125">See Also</span></span>  
 [<span data-ttu-id="c0eae-126">创建 PeopleSoft HTTP 主机和端口</span><span class="sxs-lookup"><span data-stu-id="c0eae-126">Creating a PeopleSoft HTTP Host and Port</span></span>](../core/creating-a-peoplesoft-http-host-and-port.md)