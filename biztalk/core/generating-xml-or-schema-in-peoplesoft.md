---
title: 在 PeopleSoft 中生成 XML 或架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- generating schemas
- schemas, generating
- generating XML
- XML, generating
ms.assetid: adfe2936-0dc2-42d2-b26a-718f8cc57eff
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3046a6cb3dc90db69d7d113bf08b92d8c4606bab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387748"
---
# <a name="generating-xml-or-schema-in-peoplesoft"></a><span data-ttu-id="f1a77-102">在 PeopleSoft 中生成 XML 或架构</span><span class="sxs-lookup"><span data-stu-id="f1a77-102">Generating XML or Schema in PeopleSoft</span></span>
<span data-ttu-id="f1a77-103">以下过程介绍如何使用 PeopleSoft Enterprise 来创建一个 XML 文件和触发 PeopleSoft 事件。</span><span class="sxs-lookup"><span data-stu-id="f1a77-103">The following procedure describes how to use PeopleSoft Enterprise to create an XML file and trigger a PeopleSoft event.</span></span> <span data-ttu-id="f1a77-104">若要执行此操作，则更改 PeopleSoft 环境中的某些内容。</span><span class="sxs-lookup"><span data-stu-id="f1a77-104">To do this, you change something in the PeopleSoft environment.</span></span> <span data-ttu-id="f1a77-105">此更改将激活发送到要监视您的业务流程中设置的文件文件夹的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="f1a77-105">The change activates an XML file, which is sent to the file folder that you set in your orchestration to be monitored.</span></span> <span data-ttu-id="f1a77-106">更高版本，在 BizTalk Server 中，您导入 XML 并生成架构。</span><span class="sxs-lookup"><span data-stu-id="f1a77-106">Later, in BizTalk Server, you import the XML and generate a schema.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f1a77-107">对位置值所做的任何更改时将位置与 MSEXTERNAL 节点相关联，生成 XML 文档 — 触发事件。</span><span class="sxs-lookup"><span data-stu-id="f1a77-107">When you associate the Location with the MSEXTERNAL node, any change made to Location Value generates an XML document—triggering an event.</span></span> <span data-ttu-id="f1a77-108">登记并启动后您的业务流程，可以通过 PeopleSoft 屏幕到 LOCATION 屏幕中进行导航。</span><span class="sxs-lookup"><span data-stu-id="f1a77-108">After enlisting and starting your orchestration, you can navigate through the PeopleSoft screens to the LOCATION screen.</span></span> <span data-ttu-id="f1a77-109">如果对位置值进行更改并保存所做的更改时，相应 XML 将出现在 \out 目录中。</span><span class="sxs-lookup"><span data-stu-id="f1a77-109">If you make a change to Location Value and save your change, a corresponding XML appears in your \out directory.</span></span>  
  
### <a name="to-generate-xml-or-schema-in-peoplesoft"></a><span data-ttu-id="f1a77-110">若要在 PeopleSoft 中生成 XML 或架构</span><span class="sxs-lookup"><span data-stu-id="f1a77-110">To generate XML or Schema in PeopleSoft</span></span>  
  
1. <span data-ttu-id="f1a77-111">在 PeopleSoft 应用程序，指向**设置财务**，依次指向**供应链**，指向**常见定义**，指向**位置**，然后选择**位置**。</span><span class="sxs-lookup"><span data-stu-id="f1a77-111">In the PeopleSoft application, point to **Set up Financials**, point to **Supply Chain**, point to **Common Definitions**, point to **Location**, and then select **Location**.</span></span>  
  
2. <span data-ttu-id="f1a77-112">上**位置**屏幕上，输入以下信息：</span><span class="sxs-lookup"><span data-stu-id="f1a77-112">On the **Location** screen, enter the following information:</span></span>  
  
   - <span data-ttu-id="f1a77-113">**设置 ID:** 输入**共享**。</span><span class="sxs-lookup"><span data-stu-id="f1a77-113">**Set ID:** Enter **SHARE**.</span></span>  
  
   - <span data-ttu-id="f1a77-114">**位置代码：** 输入代码开头的`WKLOC`。</span><span class="sxs-lookup"><span data-stu-id="f1a77-114">**Location Code:** Enter a code that starts with `WKLOC`.</span></span>  
  
     <span data-ttu-id="f1a77-115">![](../core/media/psadapter-18-task-sharesearch.gif "PSAdapter_18_Task_ShareSearch")</span><span class="sxs-lookup"><span data-stu-id="f1a77-115">![](../core/media/psadapter-18-task-sharesearch.gif "PSAdapter_18_Task_ShareSearch")</span></span>  
  
3. <span data-ttu-id="f1a77-116">单击**搜索**，然后单击**正确历史记录**若要将屏幕置于**编辑**模式。</span><span class="sxs-lookup"><span data-stu-id="f1a77-116">Click **Search**, and then click **Correct History** to put the screen in **Edit** mode.</span></span>  
  
    <span data-ttu-id="f1a77-117">![](../core/media/psadapter-19-task-correcthistory.gif "PSAdapter_19_Task_CorrectHistory")</span><span class="sxs-lookup"><span data-stu-id="f1a77-117">![](../core/media/psadapter-19-task-correcthistory.gif "PSAdapter_19_Task_CorrectHistory")</span></span>  
  
4. <span data-ttu-id="f1a77-118">请在屏幕上的字段进行的更改，然后依次**保存**。</span><span class="sxs-lookup"><span data-stu-id="f1a77-118">Make a change to a field on the screen, and then click **Save**.</span></span>  
  
5. <span data-ttu-id="f1a77-119">指向**PeopleTools**，依次指向**Integration Broker**，指向**监视器**，然后选择**监视器消息**。</span><span class="sxs-lookup"><span data-stu-id="f1a77-119">Point to **PeopleTools**, point to **Integration Broker**, point to **Monitor**, and then select **Monitor Message**.</span></span>  
  
    <span data-ttu-id="f1a77-120">![](../core/media/psadapter-20-task-monitormessage.gif "PSAdapter_20_Task_MonitorMessage")</span><span class="sxs-lookup"><span data-stu-id="f1a77-120">![](../core/media/psadapter-20-task-monitormessage.gif "PSAdapter_20_Task_MonitorMessage")</span></span>  
  
6. <span data-ttu-id="f1a77-121">请确保**通道类型**是**消息实例**，然后单击**刷新**。</span><span class="sxs-lookup"><span data-stu-id="f1a77-121">Make sure that **Channel Type** is **Message Instance**, and then click **Refresh**.</span></span>  
  
7. <span data-ttu-id="f1a77-122">在中**完成**列中，单击的数字。</span><span class="sxs-lookup"><span data-stu-id="f1a77-122">In the **Done** column, click the number.</span></span>  
  
8. <span data-ttu-id="f1a77-123">滚动到列表的底部，单击**详细信息**链接**LOCATION_SYNC**消息。</span><span class="sxs-lookup"><span data-stu-id="f1a77-123">Scroll to the bottom of the list and click the **Details** link on a **LOCATION_SYNC** message.</span></span>  
  
    <span data-ttu-id="f1a77-124">![](../core/media/psadapter-21-task-detailslink.gif "PSAdapter_21_Task_DetailsLink")</span><span class="sxs-lookup"><span data-stu-id="f1a77-124">![](../core/media/psadapter-21-task-detailslink.gif "PSAdapter_21_Task_DetailsLink")</span></span>  
  
9. <span data-ttu-id="f1a77-125">单击**查看 XML**上**MSEXTERNAL**节点。</span><span class="sxs-lookup"><span data-stu-id="f1a77-125">Click **View XML** on a **MSEXTERNAL** Node.</span></span>  
  
     <span data-ttu-id="f1a77-126">![](../core/media/psadapter-22-task-viewxml.gif "PSAdapter_22_Task_ViewXML")</span><span class="sxs-lookup"><span data-stu-id="f1a77-126">![](../core/media/psadapter-22-task-viewxml.gif "PSAdapter_22_Task_ViewXML")</span></span>  
  
     <span data-ttu-id="f1a77-127">复制并粘贴到可以访问由 BizTalk Server 项目的文件的 XML 内容。</span><span class="sxs-lookup"><span data-stu-id="f1a77-127">Copy and paste the contents of the XML into a file that can be accessed by your BizTalk Server project.</span></span>  
  
     <span data-ttu-id="f1a77-128">![](../core/media/psadapter-23-task-xmlresult.gif "PSAdapter_23_Task_XMLResult")</span><span class="sxs-lookup"><span data-stu-id="f1a77-128">![](../core/media/psadapter-23-task-xmlresult.gif "PSAdapter_23_Task_XMLResult")</span></span>  
  
10. <span data-ttu-id="f1a77-129">请记住文件的位置; 在 BizTalk Server 中引用它。</span><span class="sxs-lookup"><span data-stu-id="f1a77-129">Remember the location of the file;  you reference it in BizTalk Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1a77-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="f1a77-130">See Also</span></span>  
 [<span data-ttu-id="f1a77-131">附录 b:使用 PeopleSoft 应用程序</span><span class="sxs-lookup"><span data-stu-id="f1a77-131">Appendix B: Using the PeopleSoft Application</span></span>](../core/appendix-b-using-the-peoplesoft-application.md)