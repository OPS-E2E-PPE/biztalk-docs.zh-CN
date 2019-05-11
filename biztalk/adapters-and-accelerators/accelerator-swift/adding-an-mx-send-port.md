---
title: 添加 MX 发送端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c3ad5d2f-1fcb-49d4-9974-664733308f45
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 878353f8082ba7990c6e15bc46876544b83e9508
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378694"
---
# <a name="adding-an-mx-send-port"></a><span data-ttu-id="66e3a-102">添加 MX 发送端口</span><span class="sxs-lookup"><span data-stu-id="66e3a-102">Adding an MX Send Port</span></span>
<span data-ttu-id="66e3a-103">**若要添加 MX 发送端口：**</span><span class="sxs-lookup"><span data-stu-id="66e3a-103">**To add an MX send port:**</span></span>  
  
1.  <span data-ttu-id="66e3a-104">在 BizTalk Server 管理控制台中，右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="66e3a-104">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-Way Send Port**.</span></span>  
  
2.  <span data-ttu-id="66e3a-105">在发送端口属性对话框中，在名称框中键入**MX_SendPort**。</span><span class="sxs-lookup"><span data-stu-id="66e3a-105">In the Send Port Properties dialog box, in the Name box type **MX_SendPort**.</span></span>  
  
3.  <span data-ttu-id="66e3a-106">在传输部分的类型框中，单击下拉列表，然后选择**文件**。</span><span class="sxs-lookup"><span data-stu-id="66e3a-106">In the Transport section, for the Type box, click the drop-down list, and then select **FILE**.</span></span>  
  
4.  <span data-ttu-id="66e3a-107">单击**配置**类型下拉列表右侧的按钮。</span><span class="sxs-lookup"><span data-stu-id="66e3a-107">Click the **Configure** button to the right of the Type drop-down list.</span></span>  
  
5.  <span data-ttu-id="66e3a-108">在 FILE 传输属性对话框中，单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="66e3a-108">In the FILE Transport Properties dialog box, click **Browse**.</span></span>  
  
6.  <span data-ttu-id="66e3a-109">在浏览文件夹对话框中，选择文件位置。</span><span class="sxs-lookup"><span data-stu-id="66e3a-109">In the Browse for Folder dialog box, select a file location.</span></span>  
  
7.  <span data-ttu-id="66e3a-110">在文件名框中，键入 **%MessageID%.xml**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="66e3a-110">In the File name box, type **%MessageID%.xml**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="66e3a-111">在发送端口属性对话框中，单击发送管道框中的下拉列表，然后选择管道项目中的已部署的发送管道。</span><span class="sxs-lookup"><span data-stu-id="66e3a-111">In the Send Port Properties dialog box, click the drop-down list for the send pipeline box, and then select the send pipeline you have deployed in the pipeline project.</span></span>  
  
9. <span data-ttu-id="66e3a-112">在左窗格中，单击**筛选器**，然后指定以下：</span><span class="sxs-lookup"><span data-stu-id="66e3a-112">In the left pane, click **Filters**, and then specify the following:</span></span>  
  
    |||  
    |-|-|  
    |<span data-ttu-id="66e3a-113">属性</span><span class="sxs-lookup"><span data-stu-id="66e3a-113">Property</span></span>|<span data-ttu-id="66e3a-114">Microsoft.Solutions.MX_A4SWIFT.Property.MX_A4SWIFT_Failed</span><span class="sxs-lookup"><span data-stu-id="66e3a-114">Microsoft.Solutions.MX_A4SWIFT.Property.MX_A4SWIFT_Failed</span></span>|  
    |<span data-ttu-id="66e3a-115">运算符</span><span class="sxs-lookup"><span data-stu-id="66e3a-115">Operator</span></span>|<span data-ttu-id="66e3a-116">选择 = =</span><span class="sxs-lookup"><span data-stu-id="66e3a-116">Select ==</span></span>|  
    |<span data-ttu-id="66e3a-117">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="66e3a-117">Value</span></span>|<span data-ttu-id="66e3a-118">False</span><span class="sxs-lookup"><span data-stu-id="66e3a-118">False</span></span>|  
  
10. <span data-ttu-id="66e3a-119">单击**Apply**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="66e3a-119">Click **Apply**, and then click **OK**.</span></span>  
  
11. <span data-ttu-id="66e3a-120">在发送端口窗格中，右键单击**MX_SendPort**，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="66e3a-120">In the Send Ports pane, right-click **MX_SendPort**, and then click **Start**.</span></span>