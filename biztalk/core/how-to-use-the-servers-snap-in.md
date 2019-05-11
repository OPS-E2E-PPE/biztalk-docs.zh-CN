---
title: 如何使用服务器管理单元 |Microsoft Docs
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
ms.openlocfilehash: 094bf6ac21aff4d65528db4ae105cb3081405210
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383198"
---
# <a name="how-to-use-the-servers-snap-in"></a><span data-ttu-id="d43cb-102">如何使用服务器管理单元</span><span class="sxs-lookup"><span data-stu-id="d43cb-102">How to Use the Servers Snap-in</span></span>
<span data-ttu-id="d43cb-103">此版本的企业单一登录 (SSO) 包括 ENTSSO 服务器管理单元中，以便您可以查看、 监视和通过 Windows 界面在 ENTSSO 服务器上执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="d43cb-103">This version of Enterprise Single Sign-On (SSO) includes the ENTSSO Servers Snap-In, which allows you to view, monitor, and perform certain actions on your ENTSSO Server through the Windows interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d43cb-104">如果您的系统具有防火墙且服务器名称使用 FQDN 格式，您可能无法联系服务器。</span><span class="sxs-lookup"><span data-stu-id="d43cb-104">If your system has a firewall and your server name uses the FQDN format, you may not be able to contact the server.</span></span> <span data-ttu-id="d43cb-105">相反，必须指定 NetBIOS 名称或关联的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="d43cb-105">Instead, you must specify the NetBIOS name or the associated IP address.</span></span>  
  
### <a name="to-use-the-entsso-servers-snap-in"></a><span data-ttu-id="d43cb-106">若要使用 ENTSSO 服务器管理单元</span><span class="sxs-lookup"><span data-stu-id="d43cb-106">To use the ENTSSO Servers Snap-In</span></span>  
  
1.  <span data-ttu-id="d43cb-107">打开企业单一登录。</span><span class="sxs-lookup"><span data-stu-id="d43cb-107">Open Enterprise Single Sign-On.</span></span>  
  
2.  <span data-ttu-id="d43cb-108">在作用域窗格中，单击**服务器**节点。</span><span class="sxs-lookup"><span data-stu-id="d43cb-108">In the Scope pane, click the **Servers** node.</span></span>  
  
     <span data-ttu-id="d43cb-109">在结果窗格中显示以下信息。</span><span class="sxs-lookup"><span data-stu-id="d43cb-109">The following information is displayed in the Results pane.</span></span>  
  
    -   <span data-ttu-id="d43cb-110">**名称**：指定的名称。</span><span class="sxs-lookup"><span data-stu-id="d43cb-110">**Name**: Name specified.</span></span>  
  
    -   <span data-ttu-id="d43cb-111">**状态**：ENTSSO 服务 （联机、 脱机、 挂起、 启动、 停止、 启动挂起、 停止挂起） 的状态。</span><span class="sxs-lookup"><span data-stu-id="d43cb-111">**Status**: Status of the ENTSSO service (Online, Offline, Pending, Started, Stopped, Start Pending, Stop Pending).</span></span>  
  
    -   <span data-ttu-id="d43cb-112">**日期**:获得信息的日期。</span><span class="sxs-lookup"><span data-stu-id="d43cb-112">**Date**: Date when information was obtained.</span></span>  
  
    -   <span data-ttu-id="d43cb-113">**时间**:获得信息的时间。</span><span class="sxs-lookup"><span data-stu-id="d43cb-113">**Time**: Time when information was obtained.</span></span>  
  
    -   <span data-ttu-id="d43cb-114">**SSO 服务器**:服务器的完全限定的名称。</span><span class="sxs-lookup"><span data-stu-id="d43cb-114">**SSO Server**: Fully qualified name of server.</span></span>  
  
    -   <span data-ttu-id="d43cb-115">**服务帐户**:ENTSSO 服务帐户。</span><span class="sxs-lookup"><span data-stu-id="d43cb-115">**Service Account**: ENTSSO service account.</span></span>  
  
    -   <span data-ttu-id="d43cb-116">**SSO 数据库**:与此服务器通信的 ENTSSO 数据库。</span><span class="sxs-lookup"><span data-stu-id="d43cb-116">**SSO Database**: ENTSSO Database with which this server is communicating.</span></span>  
  
    -   <span data-ttu-id="d43cb-117">**密钥服务器**:指示密钥服务器模块是否正在运行。</span><span class="sxs-lookup"><span data-stu-id="d43cb-117">**Secret Server**: Indicates whether the Secret Server module is running.</span></span>  
  
    -   <span data-ttu-id="d43cb-118">**密码同步**:指示是否已安装密码同步。</span><span class="sxs-lookup"><span data-stu-id="d43cb-118">**Password Sync**: Indicates whether Password Sync is installed.</span></span>  
  
    -   <span data-ttu-id="d43cb-119">**计算机**:计算机的 NETBIOS 名称。</span><span class="sxs-lookup"><span data-stu-id="d43cb-119">**Computer**: NETBIOS name of computer.</span></span>  
  
    -   <span data-ttu-id="d43cb-120">**事件计数**:信息/警告/错误事件计数。</span><span class="sxs-lookup"><span data-stu-id="d43cb-120">**Event counts**: Info/Warning/Errors event count.</span></span> <span data-ttu-id="d43cb-121">重置将计数器从 0 开始。</span><span class="sxs-lookup"><span data-stu-id="d43cb-121">Resetting this will start the counter from 0.</span></span>  
  
    -   <span data-ttu-id="d43cb-122">**安装的 SSO 版本**:ENTSSO.exe 的版本号。</span><span class="sxs-lookup"><span data-stu-id="d43cb-122">**Version of SSO installed**: Version number of ENTSSO.exe.</span></span> <span data-ttu-id="d43cb-123">此外指示这是否 (x86) 32 位或 64 位 (x64)。</span><span class="sxs-lookup"><span data-stu-id="d43cb-123">Also indicates whether this is 32-bit (x86) or 64-bit (x64).</span></span>  
  
### <a name="to-start-or-stop-the-server-service"></a><span data-ttu-id="d43cb-124">若要启动或停止服务器服务</span><span class="sxs-lookup"><span data-stu-id="d43cb-124">To start or stop the server service</span></span>  
  
-   <span data-ttu-id="d43cb-125">在 ENTSSO 服务器管理单元中，右键单击服务器，然后单击**启动**或**停止**。</span><span class="sxs-lookup"><span data-stu-id="d43cb-125">In the ENTSSO Servers Snap-In, right-click the server and click **Start** or **Stop**.</span></span>  
  
### <a name="to-display-information-for-one-server"></a><span data-ttu-id="d43cb-126">若要显示的一台服务器的信息</span><span class="sxs-lookup"><span data-stu-id="d43cb-126">To display information for one server</span></span>  
  
-   <span data-ttu-id="d43cb-127">在服务器树中，单击服务器。</span><span class="sxs-lookup"><span data-stu-id="d43cb-127">In the Server tree, click the server.</span></span>  
  
     <span data-ttu-id="d43cb-128">在结果窗格中显示的信息。</span><span class="sxs-lookup"><span data-stu-id="d43cb-128">The information is displayed in the results pane.</span></span>  
  
### <a name="to-add-a-server"></a><span data-ttu-id="d43cb-129">若要添加服务器</span><span class="sxs-lookup"><span data-stu-id="d43cb-129">To add a server</span></span>  
  
-   <span data-ttu-id="d43cb-130">在作用域窗格中，右键单击，然后单击**添加服务器**。</span><span class="sxs-lookup"><span data-stu-id="d43cb-130">Right-click in the Scope pane, and then click **Add Server**.</span></span>  
  
     <span data-ttu-id="d43cb-131">**添加服务器**对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="d43cb-131">The **Add Server** dialog box appears.</span></span> <span data-ttu-id="d43cb-132">键入或浏览到想要添加的服务器。</span><span class="sxs-lookup"><span data-stu-id="d43cb-132">Type or browse to the server you want to add.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d43cb-133">在某些工作组环境中，单击**浏览**按钮都将导致关闭此对话框。</span><span class="sxs-lookup"><span data-stu-id="d43cb-133">In certain Workgroup environments, clicking the **Browse** button will cause this dialog box to close.</span></span> <span data-ttu-id="d43cb-134">而不是使用**浏览**按钮，只需在框中键入服务器名称。</span><span class="sxs-lookup"><span data-stu-id="d43cb-134">Instead of using the **Browse** button, simply type the server name in the box.</span></span>  
  
### <a name="to-view-or-change-server-properties"></a><span data-ttu-id="d43cb-135">查看或更改服务器属性</span><span class="sxs-lookup"><span data-stu-id="d43cb-135">To view or change server properties</span></span>  
  
-   <span data-ttu-id="d43cb-136">在服务器树中，右键单击服务器，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="d43cb-136">In the Server tree, right-click the server, and click **Properties**.</span></span>  
  
     <span data-ttu-id="d43cb-137">**服务器属性**对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="d43cb-137">The **Server Properties** dialog box appears.</span></span> <span data-ttu-id="d43cb-138">您可以查看或更改以下选项卡中的信息：</span><span class="sxs-lookup"><span data-stu-id="d43cb-138">You can view or change information in the following tabs:</span></span>  
  
    -   <span data-ttu-id="d43cb-139">**审核级别**</span><span class="sxs-lookup"><span data-stu-id="d43cb-139">**Audit Levels**</span></span>  
  
    -   <span data-ttu-id="d43cb-140">**SSO 数据库**</span><span class="sxs-lookup"><span data-stu-id="d43cb-140">**SSO Database**</span></span>  
  
    -   <span data-ttu-id="d43cb-141">**SSO 服务**</span><span class="sxs-lookup"><span data-stu-id="d43cb-141">**SSO Service**</span></span>  
  
    -   <span data-ttu-id="d43cb-142">**密码同步**</span><span class="sxs-lookup"><span data-stu-id="d43cb-142">**Password Sync**</span></span>  
  
    -   <span data-ttu-id="d43cb-143">**高级**</span><span class="sxs-lookup"><span data-stu-id="d43cb-143">**Advanced**</span></span>