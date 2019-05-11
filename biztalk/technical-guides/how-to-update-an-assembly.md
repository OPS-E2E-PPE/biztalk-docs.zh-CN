---
title: 如何更新程序集 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4f456c8f-247a-4d5c-b5af-41e88968779c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68af9966181209b50a4cfb5ee484264d32c60d4c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401807"
---
# <a name="how-to-update-an-assembly"></a><span data-ttu-id="71391-102">如何更新程序集</span><span class="sxs-lookup"><span data-stu-id="71391-102">How to Update an Assembly</span></span>
<span data-ttu-id="71391-103">本主题介绍如何更新的程序集和应用程序程序集部署到使用 Visual Studio 2010 版本。</span><span class="sxs-lookup"><span data-stu-id="71391-103">This topic describes how to update the version of an assembly and the application that an assembly is deployed to using Visual Studio 2010.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="71391-104">如果要使用新版本更新程序集，您不需要重新启动该应用程序。</span><span class="sxs-lookup"><span data-stu-id="71391-104">If you are updating an assembly with a new version, you do not need to restart the application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="71391-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="71391-105">Prerequisites</span></span>  
 <span data-ttu-id="71391-106">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="71391-106">To perform the procedures in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span>  
  
## <a name="updating-an-assembly"></a><span data-ttu-id="71391-107">更新的程序集</span><span class="sxs-lookup"><span data-stu-id="71391-107">Updating an Assembly</span></span>  
  
#### <a name="to-increment-the-version-number-of-an-assembly"></a><span data-ttu-id="71391-108">若要递增程序集的版本号</span><span class="sxs-lookup"><span data-stu-id="71391-108">To increment the version number of an assembly</span></span>  
  
1.  <span data-ttu-id="71391-109">在解决方案资源管理器，右键单击 BizTalk 项目，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="71391-109">In Solution Explorer, right-click the BizTalk project, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="71391-110">在中**项目设计器**，单击**应用程序**选项卡。</span><span class="sxs-lookup"><span data-stu-id="71391-110">In the **Project Designer**, click the **Application** tab.</span></span>  
  
3.  <span data-ttu-id="71391-111">在右窗格中，单击**程序集信息**。</span><span class="sxs-lookup"><span data-stu-id="71391-111">In the right pane, click **Assembly Information**.</span></span>  
  
4.  <span data-ttu-id="71391-112">在中**程序集信息**对话框框中，为指定值**程序集版本**字段以增加程序集的版本号。</span><span class="sxs-lookup"><span data-stu-id="71391-112">In the **Assembly Information** dialog box, specify values for the **Assembly Version** field to increase the assembly version number.</span></span> <span data-ttu-id="71391-113">应增加仅主要或次要版本数。</span><span class="sxs-lookup"><span data-stu-id="71391-113">You should increase only the major or minor version number.</span></span> <span data-ttu-id="71391-114">主版本号是序列中的第一个数字 (***n***.0.0.0); 次版本号是序列中的第二个数字 (0。***n***.0.0)。</span><span class="sxs-lookup"><span data-stu-id="71391-114">The major version number is the first digit in the sequence (***n***.0.0.0); the minor version number is the second digit in the sequence (0.***n***.0.0).</span></span> <span data-ttu-id="71391-115">BizTalk Server 将无法识别版本号的更改是在序列中，例如 0.0 更高版本。***n***.0 或 0.0.0。***n***。</span><span class="sxs-lookup"><span data-stu-id="71391-115">BizTalk Server will not recognize a version number change that is later in the sequence, such as 0.0.***n***.0 or 0.0.0.***n***.</span></span>  
  
5.  <span data-ttu-id="71391-116">单击**确定**以关闭**程序集信息**对话框。</span><span class="sxs-lookup"><span data-stu-id="71391-116">Click **OK** to close the **Assembly Information** dialog box.</span></span>  
  
6.  <span data-ttu-id="71391-117">保存项目。</span><span class="sxs-lookup"><span data-stu-id="71391-117">Save the project.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="71391-118">使用管道设计器和 BizTalk 浏览器对象模型以避免架构冲突时递增程序集版本。</span><span class="sxs-lookup"><span data-stu-id="71391-118">Use the Pipeline Designer and BizTalk Explorer Object Model to avoid schema collisions when incrementing assembly versions.</span></span>  
  
#### <a name="to-change-the-application-that-an-assembly-is-deployed-to"></a><span data-ttu-id="71391-119">若要更改程序集部署到的应用程序</span><span class="sxs-lookup"><span data-stu-id="71391-119">To change the application that an assembly is deployed to</span></span>  
  
1.  <span data-ttu-id="71391-120">在解决方案资源管理器，右键单击 BizTalk 项目，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="71391-120">In Solution Explorer, right-click the BizTalk project, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="71391-121">在中**项目设计器**，单击**部署**选项卡。</span><span class="sxs-lookup"><span data-stu-id="71391-121">In the **Project Designer**, click the **Deployment** tab.</span></span>  
  
3.  <span data-ttu-id="71391-122">在右窗格中，指定在应用程序名称**应用程序名称**字段。</span><span class="sxs-lookup"><span data-stu-id="71391-122">In the right pane, specify the application name in the **Application Name** field.</span></span>  
  
4.  <span data-ttu-id="71391-123">絋粄**安装到全局程序集缓存**属性设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="71391-123">Ensure that the **Install to Global Assembly Cache** property is set to **True**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="71391-124">在部署解决方案时，将部署到新的应用程序并安装到 GAC 中程序集。</span><span class="sxs-lookup"><span data-stu-id="71391-124">When you deploy the solution, the assemblies will be deployed into the new application and installed in the GAC.</span></span>