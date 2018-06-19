---
title: 如何使用服务器管理单元 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4f520692-9606-41f5-98ed-5a4962bd1f09
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12eb72323a6dcd1132f03febc9b4d9bd75316c84
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256557"
---
# <a name="how-to-use-the-servers-snap-in"></a><span data-ttu-id="8bf8e-102">如何使用服务器管理单元</span><span class="sxs-lookup"><span data-stu-id="8bf8e-102">How to Use the Servers Snap-in</span></span>
<span data-ttu-id="8bf8e-103">此版本的企业单一登录 (SSO) 包括 ENTSSO 服务器管理单元，您可用利用它通过 Windows 界面查看、监视 ENTSSO 服务器上的某些操作，以及在该服务器上执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="8bf8e-103">This version of Enterprise Single Sign-On (SSO) includes the ENTSSO Servers Snap-In, which allows you to view, monitor, and perform certain actions on your ENTSSO Server through the Windows interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8bf8e-104">如果系统具有防火墙且服务器名称使用的是 FQDN 格式，则可能无法与服务器取得联系。</span><span class="sxs-lookup"><span data-stu-id="8bf8e-104">If your system has a firewall and your server name uses the FQDN format, you may not be able to contact the server.</span></span> <span data-ttu-id="8bf8e-105">因此，您必须指定 NetBIOS 名称或相关的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="8bf8e-105">Instead, you must specify the NetBIOS name or the associated IP address.</span></span>  
  
### <a name="to-use-the-entsso-servers-snap-in"></a><span data-ttu-id="8bf8e-106">使用 ENTSSO 服务器管理单元</span><span class="sxs-lookup"><span data-stu-id="8bf8e-106">To use the ENTSSO Servers Snap-In</span></span>  
  
1.  <span data-ttu-id="8bf8e-107">打开企业单一登录。</span><span class="sxs-lookup"><span data-stu-id="8bf8e-107">Open Enterprise Single Sign-On.</span></span>  
  
2.  <span data-ttu-id="8bf8e-108">在作用域窗格中，单击**服务器**节点。</span><span class="sxs-lookup"><span data-stu-id="8bf8e-108">In the Scope pane, click the **Servers** node.</span></span>  
  
     <span data-ttu-id="8bf8e-109">结果窗格中会显示的以下信息。</span><span class="sxs-lookup"><span data-stu-id="8bf8e-109">The following information is displayed in the Results pane.</span></span>  
  
    -   <span data-ttu-id="8bf8e-110">**名称**： 指定的名称。</span><span class="sxs-lookup"><span data-stu-id="8bf8e-110">**Name**: Name specified.</span></span>  
  
    -   <span data-ttu-id="8bf8e-111">**状态**: ENTSSO 服务 （联机状态，脱机，挂起、 启动、 停止、 启动挂起、 停止挂起） 的状态。</span><span class="sxs-lookup"><span data-stu-id="8bf8e-111">**Status**: Status of the ENTSSO service (Online, Offline, Pending, Started, Stopped, Start Pending, Stop Pending).</span></span>  
  
    -   <span data-ttu-id="8bf8e-112">**日期**： 时获取信息的日期。</span><span class="sxs-lookup"><span data-stu-id="8bf8e-112">**Date**: Date when information was obtained.</span></span>  
  
    -   <span data-ttu-id="8bf8e-113">**时间**： 时获取信息的时间。</span><span class="sxs-lookup"><span data-stu-id="8bf8e-113">**Time**: Time when information was obtained.</span></span>  
  
    -   <span data-ttu-id="8bf8e-114">**SSO 服务器**： 服务器的完全限定的名称。</span><span class="sxs-lookup"><span data-stu-id="8bf8e-114">**SSO Server**: Fully qualified name of server.</span></span>  
  
    -   <span data-ttu-id="8bf8e-115">**服务帐户**: ENTSSO 服务帐户。</span><span class="sxs-lookup"><span data-stu-id="8bf8e-115">**Service Account**: ENTSSO service account.</span></span>  
  
    -   <span data-ttu-id="8bf8e-116">**SSO 数据库**: ENTSSO 数据库与此服务器通信。</span><span class="sxs-lookup"><span data-stu-id="8bf8e-116">**SSO Database**: ENTSSO Database with which this server is communicating.</span></span>  
  
    -   <span data-ttu-id="8bf8e-117">**密钥服务器**： 指示是否正在运行的服务器模块。</span><span class="sxs-lookup"><span data-stu-id="8bf8e-117">**Secret Server**: Indicates whether the Secret Server module is running.</span></span>  
  
    -   <span data-ttu-id="8bf8e-118">**密码同步**： 指示是否安装了密码同步。</span><span class="sxs-lookup"><span data-stu-id="8bf8e-118">**Password Sync**: Indicates whether Password Sync is installed.</span></span>  
  
    -   <span data-ttu-id="8bf8e-119">**计算机**： 计算机的 NETBIOS 名称。</span><span class="sxs-lookup"><span data-stu-id="8bf8e-119">**Computer**: NETBIOS name of computer.</span></span>  
  
    -   <span data-ttu-id="8bf8e-120">**事件都统计**： 信息/警告/错误事件计数。</span><span class="sxs-lookup"><span data-stu-id="8bf8e-120">**Event counts**: Info/Warning/Errors event count.</span></span> <span data-ttu-id="8bf8e-121">将其重置会使计数器从 0 开始计数。</span><span class="sxs-lookup"><span data-stu-id="8bf8e-121">Resetting this will start the counter from 0.</span></span>  
  
    -   <span data-ttu-id="8bf8e-122">**安装的 SSO 版本**: ENTSSO.exe 版本号。</span><span class="sxs-lookup"><span data-stu-id="8bf8e-122">**Version of SSO installed**: Version number of ENTSSO.exe.</span></span> <span data-ttu-id="8bf8e-123">此外指示这是 32 位 (x86) 还是 64 位 (x64)。</span><span class="sxs-lookup"><span data-stu-id="8bf8e-123">Also indicates whether this is 32-bit (x86) or 64-bit (x64).</span></span>  
  
### <a name="to-start-or-stop-the-server-service"></a><span data-ttu-id="8bf8e-124">启动或停止服务器服务</span><span class="sxs-lookup"><span data-stu-id="8bf8e-124">To start or stop the server service</span></span>  
  
-   <span data-ttu-id="8bf8e-125">ENTSSO 服务器管理单元中，右键单击服务器，然后单击**启动**或**停止**。</span><span class="sxs-lookup"><span data-stu-id="8bf8e-125">In the ENTSSO Servers Snap-In, right-click the server and click **Start** or **Stop**.</span></span>  
  
### <a name="to-display-information-for-one-server"></a><span data-ttu-id="8bf8e-126">显示一个服务器的信息</span><span class="sxs-lookup"><span data-stu-id="8bf8e-126">To display information for one server</span></span>  
  
-   <span data-ttu-id="8bf8e-127">在服务器树中，单击该服务器。</span><span class="sxs-lookup"><span data-stu-id="8bf8e-127">In the Server tree, click the server.</span></span>  
  
     <span data-ttu-id="8bf8e-128">信息将显示在结果窗格中。</span><span class="sxs-lookup"><span data-stu-id="8bf8e-128">The information is displayed in the results pane.</span></span>  
  
### <a name="to-add-a-server"></a><span data-ttu-id="8bf8e-129">添加服务器</span><span class="sxs-lookup"><span data-stu-id="8bf8e-129">To add a server</span></span>  
  
-   <span data-ttu-id="8bf8e-130">在作用域窗格中，右键单击，然后单击**添加服务器**。</span><span class="sxs-lookup"><span data-stu-id="8bf8e-130">Right-click in the Scope pane, and then click **Add Server**.</span></span>  
  
     <span data-ttu-id="8bf8e-131">**添加服务器**对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="8bf8e-131">The **Add Server** dialog box appears.</span></span> <span data-ttu-id="8bf8e-132">键入或浏览到要添加的服务器。</span><span class="sxs-lookup"><span data-stu-id="8bf8e-132">Type or browse to the server you want to add.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8bf8e-133">在某些工作组环境中，单击**浏览**按钮将导致关闭此对话框。</span><span class="sxs-lookup"><span data-stu-id="8bf8e-133">In certain Workgroup environments, clicking the **Browse** button will cause this dialog box to close.</span></span> <span data-ttu-id="8bf8e-134">而不是使用**浏览**按钮，只需在框中键入服务器名称。</span><span class="sxs-lookup"><span data-stu-id="8bf8e-134">Instead of using the **Browse** button, simply type the server name in the box.</span></span>  
  
### <a name="to-view-or-change-server-properties"></a><span data-ttu-id="8bf8e-135">查看或更改服务器属性</span><span class="sxs-lookup"><span data-stu-id="8bf8e-135">To view or change server properties</span></span>  
  
-   <span data-ttu-id="8bf8e-136">在服务器树中，右键单击服务器，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="8bf8e-136">In the Server tree, right-click the server, and click **Properties**.</span></span>  
  
     <span data-ttu-id="8bf8e-137">**服务器属性**对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="8bf8e-137">The **Server Properties** dialog box appears.</span></span> <span data-ttu-id="8bf8e-138">您可以更改以下选项卡中的信息：</span><span class="sxs-lookup"><span data-stu-id="8bf8e-138">You can view or change information in the following tabs:</span></span>  
  
    -   <span data-ttu-id="8bf8e-139">**审核级别**</span><span class="sxs-lookup"><span data-stu-id="8bf8e-139">**Audit Levels**</span></span>  
  
    -   <span data-ttu-id="8bf8e-140">**SSO 数据库**</span><span class="sxs-lookup"><span data-stu-id="8bf8e-140">**SSO Database**</span></span>  
  
    -   <span data-ttu-id="8bf8e-141">**SSO 服务**</span><span class="sxs-lookup"><span data-stu-id="8bf8e-141">**SSO Service**</span></span>  
  
    -   <span data-ttu-id="8bf8e-142">**密码同步**</span><span class="sxs-lookup"><span data-stu-id="8bf8e-142">**Password Sync**</span></span>  
  
    -   <span data-ttu-id="8bf8e-143">**高级**</span><span class="sxs-lookup"><span data-stu-id="8bf8e-143">**Advanced**</span></span>