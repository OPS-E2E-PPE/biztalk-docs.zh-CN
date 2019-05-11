---
title: 如何更改跟踪 QueryTimeout 值 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- queries [HAT], time-out limits
- HAT, time-out limits
ms.assetid: abc26f37-6537-42fa-81ff-bc8b758b4e10
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77e609b5b551fc5b8c97dac704ad31e4e413426c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387022"
---
# <a name="how-to-change-the-tracking-querytimeout-value"></a><span data-ttu-id="7a25b-102">如何更改跟踪 QueryTimeout 值</span><span class="sxs-lookup"><span data-stu-id="7a25b-102">How to Change the Tracking QueryTimeout Value</span></span>
<span data-ttu-id="7a25b-103">默认情况下，消息和服务实例跟踪将超时如果查询的运行时间超过 60 秒。</span><span class="sxs-lookup"><span data-stu-id="7a25b-103">By default, message and service instance tracking will time out if a query runs longer than 60 seconds.</span></span> <span data-ttu-id="7a25b-104">你可以在注册表中启用查询运行时间超过 60 秒的超时值。</span><span class="sxs-lookup"><span data-stu-id="7a25b-104">You can change the timeout value in the registry to enable queries to run longer than 60 seconds.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="7a25b-105">错误编辑注册表可能会严重损坏您的系统。</span><span class="sxs-lookup"><span data-stu-id="7a25b-105">Incorrectly editing the registry may severely damage your system.</span></span> <span data-ttu-id="7a25b-106">更改注册表之前，应当备份计算机中的所有重要数据。</span><span class="sxs-lookup"><span data-stu-id="7a25b-106">Before making changes to the registry, you should back up any valued data on the computer.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7a25b-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="7a25b-107">Prerequisites</span></span>  
 <span data-ttu-id="7a25b-108">您必须为要执行此过程的管理员组的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="7a25b-108">You must be logged on as a member of the Administrators group to perform this procedure.</span></span>  
  
### <a name="to-change-the-query-timeout-value"></a><span data-ttu-id="7a25b-109">若要更改查询超时值</span><span class="sxs-lookup"><span data-stu-id="7a25b-109">To change the query timeout value</span></span>  
  
1.  <span data-ttu-id="7a25b-110">单击**启动**，单击**运行**，类型**regedit**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="7a25b-110">Click **Start**, click **Run**, type **regedit**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="7a25b-111">在注册表编辑器中，找到并单击以下注册表子项：</span><span class="sxs-lookup"><span data-stu-id="7a25b-111">In Registry Editor, locate and then click the following subkey:</span></span>  
  
     <span data-ttu-id="7a25b-112">**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0**</span><span class="sxs-lookup"><span data-stu-id="7a25b-112">**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0**</span></span>  
  
3.  <span data-ttu-id="7a25b-113">如果没有 Tracking 注册表子项，请转到步骤 6。</span><span class="sxs-lookup"><span data-stu-id="7a25b-113">If there is a Tracking subkey, go to step 6.</span></span>  
  
4.  <span data-ttu-id="7a25b-114">若要创建 Tracking 注册表子项，在**编辑**菜单，依次指向**新建**，然后单击**密钥**。</span><span class="sxs-lookup"><span data-stu-id="7a25b-114">To create a Tracking subkey, on the **Edit** menu, point to **New**, and then click **Key**.</span></span>  
  
5.  <span data-ttu-id="7a25b-115">类型**跟踪**，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="7a25b-115">Type **Tracking**, and then press ENTER.</span></span>  
  
6.  <span data-ttu-id="7a25b-116">找到并单击以下注册表子项：</span><span class="sxs-lookup"><span data-stu-id="7a25b-116">Locate and then click the following subkey:</span></span>  
  
     <span data-ttu-id="7a25b-117">**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0\Tracking**</span><span class="sxs-lookup"><span data-stu-id="7a25b-117">**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0\Tracking**</span></span>  
  
7.  <span data-ttu-id="7a25b-118">上**编辑**菜单，依次指向**新建**，然后单击**DWORD 值**。</span><span class="sxs-lookup"><span data-stu-id="7a25b-118">On the **Edit** menu, point to **New**, and then click **DWORD Value**.</span></span>  
  
8.  <span data-ttu-id="7a25b-119">类型**ConnectionTimeout**，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="7a25b-119">Type **ConnectionTimeout**, and then press ENTER.</span></span>  
  
9. <span data-ttu-id="7a25b-120">右键单击**ConnectionTimeout**，然后单击**修改**。</span><span class="sxs-lookup"><span data-stu-id="7a25b-120">Right-click **ConnectionTimeout**, and then click **Modify**.</span></span>  
  
10. <span data-ttu-id="7a25b-121">在中**编辑 DWORD 值**对话框中，单击**十进制**。</span><span class="sxs-lookup"><span data-stu-id="7a25b-121">In the **Edit DWORD Value** dialog box, click **Decimal**.</span></span>  
  
11. <span data-ttu-id="7a25b-122">在中**数值数据**框中，键入值以秒为单位，你想要的查询超时值，设置，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="7a25b-122">In the **Value data** box, type the value in seconds that you want to set for the query timeout value, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="7a25b-123">在 **“文件”** 菜单中，单击 **“退出”**。</span><span class="sxs-lookup"><span data-stu-id="7a25b-123">On the **File** menu, click **Exit**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7a25b-124">您可能需要关闭并重新打开 BizTalk Server 管理控制台中新的超时值的顺序才会生效。</span><span class="sxs-lookup"><span data-stu-id="7a25b-124">You may need to close and then reopen the BizTalk Server Administration Console in order for the new timeout value to take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a25b-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="7a25b-125">See Also</span></span>  
 [<span data-ttu-id="7a25b-126">查看历史数据和跟踪数据</span><span class="sxs-lookup"><span data-stu-id="7a25b-126">Viewing Historical and Tracked Data</span></span>](../core/viewing-historical-and-tracked-data.md)