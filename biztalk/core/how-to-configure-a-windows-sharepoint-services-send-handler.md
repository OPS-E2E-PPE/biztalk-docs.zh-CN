---
title: 如何配置 Windows SharePoint Services 发送处理程序 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [Windows SharePoint Services adapters], send handlers
- send handlers, Windows SharePoint Services adapters
- Windows SharePoint Services adapters, send handlers
ms.assetid: 457767d9-6e39-4553-9bbe-212fcb7c04bc
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8e110fb2a671fc839fb96cfdc2ad03169649e6e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969131"
---
# <a name="how-to-configure-a-windows-sharepoint-services-send-handler"></a><span data-ttu-id="ef142-102">如何配置 Windows SharePoint Services 发送处理程序</span><span class="sxs-lookup"><span data-stu-id="ef142-102">How to Configure a Windows SharePoint Services Send Handler</span></span>
<span data-ttu-id="ef142-103">使用以下步骤可更改与 Windows SharePoint Services 发送处理程序关联的主机。</span><span class="sxs-lookup"><span data-stu-id="ef142-103">Use the following procedure to change the host with which the Windows SharePoint Services send handler is associated.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ef142-104">每个主机只能有一个关联的发送处理程序。</span><span class="sxs-lookup"><span data-stu-id="ef142-104">Each host can have only one send handler associated with it.</span></span>  
  
### <a name="to-change-global-variables-for-a-windows-sharepoint-services-send-handler"></a><span data-ttu-id="ef142-105">更改 Windows SharePoint Services 发送处理程序的全局变量</span><span class="sxs-lookup"><span data-stu-id="ef142-105">To change global variables for a Windows SharePoint Services send handler</span></span>  
  
1.  <span data-ttu-id="ef142-106">在 BizTalk Server 管理控制台中，单击以展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，然后单击以展开**BizTalk 组 [\<servername\>:\<管理数据库\>]**，单击以展开**平台设置**，然后单击以展开**适配器**。</span><span class="sxs-lookup"><span data-stu-id="ef142-106">In the BizTalk Server Administration console, click to expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, and then click to expand **BizTalk Group [\<servername\>:\<management database\>]**, click to expand **Platform Settings**, and then click to expand **Adapters**.</span></span> <span data-ttu-id="ef142-107">此时，适配器列表将显示在该文件夹下。</span><span class="sxs-lookup"><span data-stu-id="ef142-107">The list of adapters appears under the folder.</span></span>  
  
2.  <span data-ttu-id="ef142-108">单击**Windows SharePoint Services**，然后在右窗格中，右键单击你想要配置，，然后单击发送处理程序**属性**。</span><span class="sxs-lookup"><span data-stu-id="ef142-108">Click **Windows SharePoint Services**, and in the right pane, right-click the send handler that you want to configure, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="ef142-109">在**适配器处理程序属性**对话框中，在**常规**选项卡上，在**主机名**列表中，选择发送处理程序将与之关联的主机。</span><span class="sxs-lookup"><span data-stu-id="ef142-109">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the send handler will be associated.</span></span>  
  
4.  <span data-ttu-id="ef142-110">上**常规**选项卡上，单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="ef142-110">On the **General** tab, click **Properties**.</span></span>  
  
5.  <span data-ttu-id="ef142-111">在**Windows SharePoint Services 传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ef142-111">In the **Windows SharePoint Services Transport Properties** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="ef142-112">使用此选项</span><span class="sxs-lookup"><span data-stu-id="ef142-112">Use this</span></span>|<span data-ttu-id="ef142-113">执行的操作</span><span class="sxs-lookup"><span data-stu-id="ef142-113">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="ef142-114">发送批大小</span><span class="sxs-lookup"><span data-stu-id="ef142-114">Send Batch Size</span></span>|<span data-ttu-id="ef142-115">Windows SharePoint Services Web Services 将按一批进行处理的最大文档数。</span><span class="sxs-lookup"><span data-stu-id="ef142-115">The maximum number of documents that the Windows SharePoint Services Web service will process as a batch.</span></span> <span data-ttu-id="ef142-116">默认值为 20。</span><span class="sxs-lookup"><span data-stu-id="ef142-116">The default is 20.</span></span> <span data-ttu-id="ef142-117">**注意：** 的最小值为 1。</span><span class="sxs-lookup"><span data-stu-id="ef142-117">**Note:**  The minimum value is 1.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ef142-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ef142-118">See Also</span></span>  
 <span data-ttu-id="ef142-119">[如何配置 Windows SharePoint Services 接收位置](../core/how-to-configure-a-windows-sharepoint-services-receive-location.md) </span><span class="sxs-lookup"><span data-stu-id="ef142-119">[How to Configure a Windows SharePoint Services Receive Location](../core/how-to-configure-a-windows-sharepoint-services-receive-location.md) </span></span>  
 <span data-ttu-id="ef142-120">[如何配置 Windows SharePoint Services 发送端口](../core/how-to-configure-a-windows-sharepoint-services-send-port.md) </span><span class="sxs-lookup"><span data-stu-id="ef142-120">[How to Configure a Windows SharePoint Services Send Port](../core/how-to-configure-a-windows-sharepoint-services-send-port.md) </span></span>  
 <span data-ttu-id="ef142-121">[如何创建发送端口](../core/how-to-create-a-send-port2.md) </span><span class="sxs-lookup"><span data-stu-id="ef142-121">[How to Create a Send Port](../core/how-to-create-a-send-port2.md) </span></span>  
 <span data-ttu-id="ef142-122">[Windows SharePoint Services 适配器属性参考](../core/windows-sharepoint-services-adapter-properties-reference.md) </span><span class="sxs-lookup"><span data-stu-id="ef142-122">[Windows SharePoint Services Adapter Properties Reference](../core/windows-sharepoint-services-adapter-properties-reference.md) </span></span>  
 <span data-ttu-id="ef142-123">[Windows SharePoint Services 适配器表达式](../core/windows-sharepoint-services-adapter-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="ef142-123">[Windows SharePoint Services Adapter Expressions](../core/windows-sharepoint-services-adapter-expressions.md) </span></span>  
 [<span data-ttu-id="ef142-124">支持的 Windows SharePoint Services 栏类型</span><span class="sxs-lookup"><span data-stu-id="ef142-124">Supported Windows SharePoint Services Column Types</span></span>](../core/supported-windows-sharepoint-services-column-types.md)