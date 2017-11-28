---
title: "如何更改跟踪 QueryTimeout 值 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- queries [HAT], time-out limits
- HAT, time-out limits
ms.assetid: abc26f37-6537-42fa-81ff-bc8b758b4e10
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca9f61466323e0b154bdeb0499cc5cee6e4ef10c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-change-the-tracking-querytimeout-value"></a><span data-ttu-id="c3429-102">如何更改跟踪查询超时值</span><span class="sxs-lookup"><span data-stu-id="c3429-102">How to Change the Tracking QueryTimeout Value</span></span>
<span data-ttu-id="c3429-103">默认情况下，如果查询的运行时间超过 60 秒，则消息和服务实例跟踪将超时。</span><span class="sxs-lookup"><span data-stu-id="c3429-103">By default, message and service instance tracking will time out if a query runs longer than 60 seconds.</span></span> <span data-ttu-id="c3429-104">您可以在注册表中更改该超时值，使查询的运行时间超过 60 秒。</span><span class="sxs-lookup"><span data-stu-id="c3429-104">You can change the timeout value in the registry to enable queries to run longer than 60 seconds.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="c3429-105">错误编辑注册表可能会严重损坏您的系统。</span><span class="sxs-lookup"><span data-stu-id="c3429-105">Incorrectly editing the registry may severely damage your system.</span></span> <span data-ttu-id="c3429-106">更改注册表之前，应当备份计算机中的所有重要数据。</span><span class="sxs-lookup"><span data-stu-id="c3429-106">Before making changes to the registry, you should back up any valued data on the computer.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c3429-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="c3429-107">Prerequisites</span></span>  
 <span data-ttu-id="c3429-108">必须以 Administrators 组成员的身份登录，才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="c3429-108">You must be logged on as a member of the Administrators group to perform this procedure.</span></span>  
  
### <a name="to-change-the-query-timeout-value"></a><span data-ttu-id="c3429-109">更改查询超时值的步骤</span><span class="sxs-lookup"><span data-stu-id="c3429-109">To change the query timeout value</span></span>  
  
1.  <span data-ttu-id="c3429-110">单击**启动**，单击**运行**，类型**regedit**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="c3429-110">Click **Start**, click **Run**, type **regedit**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="c3429-111">在注册表编辑器中，找到并单击以下注册表子项：</span><span class="sxs-lookup"><span data-stu-id="c3429-111">In Registry Editor, locate and then click the following subkey:</span></span>  
  
     <span data-ttu-id="c3429-112">**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0**</span><span class="sxs-lookup"><span data-stu-id="c3429-112">**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0**</span></span>  
  
3.  <span data-ttu-id="c3429-113">如果没有 Tracking 注册表子项，则转到第 6 步。</span><span class="sxs-lookup"><span data-stu-id="c3429-113">If there is a Tracking subkey, go to step 6.</span></span>  
  
4.  <span data-ttu-id="c3429-114">若要创建一个跟踪子项，在**编辑**菜单上，指向**新建**，然后单击**密钥**。</span><span class="sxs-lookup"><span data-stu-id="c3429-114">To create a Tracking subkey, on the **Edit** menu, point to **New**, and then click **Key**.</span></span>  
  
5.  <span data-ttu-id="c3429-115">类型**跟踪**，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="c3429-115">Type **Tracking**, and then press ENTER.</span></span>  
  
6.  <span data-ttu-id="c3429-116">找到并单击以下注册表子项：</span><span class="sxs-lookup"><span data-stu-id="c3429-116">Locate and then click the following subkey:</span></span>  
  
     <span data-ttu-id="c3429-117">**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0\Tracking**</span><span class="sxs-lookup"><span data-stu-id="c3429-117">**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0\Tracking**</span></span>  
  
7.  <span data-ttu-id="c3429-118">上**编辑**菜单上，指向**新建**，然后单击**DWORD 值**。</span><span class="sxs-lookup"><span data-stu-id="c3429-118">On the **Edit** menu, point to **New**, and then click **DWORD Value**.</span></span>  
  
8.  <span data-ttu-id="c3429-119">类型**ConnectionTimeout**，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="c3429-119">Type **ConnectionTimeout**, and then press ENTER.</span></span>  
  
9. <span data-ttu-id="c3429-120">右键单击**ConnectionTimeout**，然后单击**修改**。</span><span class="sxs-lookup"><span data-stu-id="c3429-120">Right-click **ConnectionTimeout**, and then click **Modify**.</span></span>  
  
10. <span data-ttu-id="c3429-121">在**编辑 DWORD 值**对话框中，单击**十进制**。</span><span class="sxs-lookup"><span data-stu-id="c3429-121">In the **Edit DWORD Value** dialog box, click **Decimal**.</span></span>  
  
11. <span data-ttu-id="c3429-122">在**值数据**框中，键入值以秒为单位你想要的查询超时值，设置，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="c3429-122">In the **Value data** box, type the value in seconds that you want to set for the query timeout value, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="c3429-123">在 **“文件”** 菜单中，单击 **“退出”**。</span><span class="sxs-lookup"><span data-stu-id="c3429-123">On the **File** menu, click **Exit**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c3429-124">您可能需要关闭后再重新打开 BizTalk Server 管理控制台，才能使新的超时值生效。</span><span class="sxs-lookup"><span data-stu-id="c3429-124">You may need to close and then reopen the BizTalk Server Administration Console in order for the new timeout value to take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3429-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c3429-125">See Also</span></span>  
 [<span data-ttu-id="c3429-126">查看历史记录和跟踪数据</span><span class="sxs-lookup"><span data-stu-id="c3429-126">Viewing Historical and Tracked Data</span></span>](../core/viewing-historical-and-tracked-data.md)