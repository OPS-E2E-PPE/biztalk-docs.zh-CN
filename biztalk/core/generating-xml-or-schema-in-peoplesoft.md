---
title: 生成 XML 或架构中 PeopleSoft |Microsoft 文档
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
ms.openlocfilehash: 1a7fbd164f7c0d380f6ee0c0fda59098203f7585
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246685"
---
# <a name="generating-xml-or-schema-in-peoplesoft"></a><span data-ttu-id="01533-102">在 PeopleSoft 中生成 XML 或架构</span><span class="sxs-lookup"><span data-stu-id="01533-102">Generating XML or Schema in PeopleSoft</span></span>
<span data-ttu-id="01533-103">以下过程介绍如何使用 PeopleSoft Enterprise 来创建 XML 文件和触发 PeopleSoft 事件。</span><span class="sxs-lookup"><span data-stu-id="01533-103">The following procedure describes how to use PeopleSoft Enterprise to create an XML file and trigger a PeopleSoft event.</span></span> <span data-ttu-id="01533-104">为此，需更改 PeopleSoft 环境中的某些内容。</span><span class="sxs-lookup"><span data-stu-id="01533-104">To do this, you change something in the PeopleSoft environment.</span></span> <span data-ttu-id="01533-105">此更改将激活发送到文件文件夹（在要监视的业务流程中设置）中的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="01533-105">The change activates an XML file, which is sent to the file folder that you set in your orchestration to be monitored.</span></span> <span data-ttu-id="01533-106">随后，在 BizTalk Server 中导入 XML 并生成架构。</span><span class="sxs-lookup"><span data-stu-id="01533-106">Later, in BizTalk Server, you import the XML and generate a schema.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="01533-107">将位置与 MSEXTERNAL 节点相关联时，对位置值所做的任何更改都会生成一个 XML 文档，从而触发事件。</span><span class="sxs-lookup"><span data-stu-id="01533-107">When you associate the Location with the MSEXTERNAL node, any change made to Location Value generates an XML document—triggering an event.</span></span> <span data-ttu-id="01533-108">在登记和启动业务流程之后，可以通过 PeopleSoft 屏幕导航到 LOCATION 屏幕。</span><span class="sxs-lookup"><span data-stu-id="01533-108">After enlisting and starting your orchestration, you can navigate through the PeopleSoft screens to the LOCATION screen.</span></span> <span data-ttu-id="01533-109">如果对位置值进行更改并保存更改，则相应 XML 将出现在 \out 目录中。</span><span class="sxs-lookup"><span data-stu-id="01533-109">If you make a change to Location Value and save your change, a corresponding XML appears in your \out directory.</span></span>  
  
### <a name="to-generate-xml-or-schema-in-peoplesoft"></a><span data-ttu-id="01533-110">若要在 PeopleSoft 中生成 XML 或架构</span><span class="sxs-lookup"><span data-stu-id="01533-110">To generate XML or Schema in PeopleSoft</span></span>  
  
1.  <span data-ttu-id="01533-111">在 PeopleSoft 应用中，依次指向**设置财务**，指向**供应链**，指向**通用定义**，指向**位置**，然后选择**位置**。</span><span class="sxs-lookup"><span data-stu-id="01533-111">In the PeopleSoft application, point to **Set up Financials**, point to **Supply Chain**, point to **Common Definitions**, point to **Location**, and then select **Location**.</span></span>  
  
2.  <span data-ttu-id="01533-112">上**位置**屏幕上，输入以下信息：</span><span class="sxs-lookup"><span data-stu-id="01533-112">On the **Location** screen, enter the following information:</span></span>  
  
    -   <span data-ttu-id="01533-113">**组 ID:** 输入**共享**。</span><span class="sxs-lookup"><span data-stu-id="01533-113">**Set ID:** Enter **SHARE**.</span></span>  
  
    -   <span data-ttu-id="01533-114">**位置代码：** 输入开头的代码`WKLOC`。</span><span class="sxs-lookup"><span data-stu-id="01533-114">**Location Code:** Enter a code that starts with `WKLOC`.</span></span>  
  
     ![](../core/media/psadapter-18-task-sharesearch.gif "PSAdapter_18_Task_ShareSearch")  
  
3.  <span data-ttu-id="01533-115">单击**搜索**，然后单击**正确历史记录**要置于屏幕**编辑**模式。</span><span class="sxs-lookup"><span data-stu-id="01533-115">Click **Search**, and then click **Correct History** to put the screen in **Edit** mode.</span></span>  
  
     ![](../core/media/psadapter-19-task-correcthistory.gif "PSAdapter_19_Task_CorrectHistory")  
  
4.  <span data-ttu-id="01533-116">在屏幕上，字段进行了更改，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="01533-116">Make a change to a field on the screen, and then click **Save**.</span></span>  
  
5.  <span data-ttu-id="01533-117">指向**PeopleTools**，指向**集成 Broker**，指向**监视器**，然后选择**监视器消息**。</span><span class="sxs-lookup"><span data-stu-id="01533-117">Point to **PeopleTools**, point to **Integration Broker**, point to **Monitor**, and then select **Monitor Message**.</span></span>  
  
     ![](../core/media/psadapter-20-task-monitormessage.gif "PSAdapter_20_Task_MonitorMessage")  
  
6.  <span data-ttu-id="01533-118">请确保**通道类型**是**消息实例**，然后单击**刷新**。</span><span class="sxs-lookup"><span data-stu-id="01533-118">Make sure that **Channel Type** is **Message Instance**, and then click **Refresh**.</span></span>  
  
7.  <span data-ttu-id="01533-119">在**完成**列中，单击的数字。</span><span class="sxs-lookup"><span data-stu-id="01533-119">In the **Done** column, click the number.</span></span>  
  
8.  <span data-ttu-id="01533-120">滚动到列表的底部，单击**详细信息**链接**LOCATION_SYNC**消息。</span><span class="sxs-lookup"><span data-stu-id="01533-120">Scroll to the bottom of the list and click the **Details** link on a **LOCATION_SYNC** message.</span></span>  
  
     ![](../core/media/psadapter-21-task-detailslink.gif "PSAdapter_21_Task_DetailsLink")  
  
9. <span data-ttu-id="01533-121">单击**查看 XML**上**MSEXTERNAL**节点。</span><span class="sxs-lookup"><span data-stu-id="01533-121">Click **View XML** on a **MSEXTERNAL** Node.</span></span>  
  
     ![](../core/media/psadapter-22-task-viewxml.gif "PSAdapter_22_Task_ViewXML")  
  
     <span data-ttu-id="01533-122">将 XML 的内容复制并粘贴到 BizTalk Server 项目可以访问的文件中。</span><span class="sxs-lookup"><span data-stu-id="01533-122">Copy and paste the contents of the XML into a file that can be accessed by your BizTalk Server project.</span></span>  
  
     ![](../core/media/psadapter-23-task-xmlresult.gif "PSAdapter_23_Task_XMLResult")  
  
10. <span data-ttu-id="01533-123">请记住该文件的位置；您将在 BizTalk Server 中引用它。</span><span class="sxs-lookup"><span data-stu-id="01533-123">Remember the location of the file;  you reference it in BizTalk Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01533-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="01533-124">See Also</span></span>  
 [<span data-ttu-id="01533-125">附录 b： 使用 PeopleSoft 应用程序</span><span class="sxs-lookup"><span data-stu-id="01533-125">Appendix B: Using the PeopleSoft Application</span></span>](../core/appendix-b-using-the-peoplesoft-application.md)