---
title: 如何更新的程序集 |Microsoft 文档
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
ms.openlocfilehash: 163b06706652b1f65b9a76e3feea8911a2ca4c88
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
ms.locfileid: "22298325"
---
# <a name="how-to-update-an-assembly"></a><span data-ttu-id="549dd-102">如何更新的程序集</span><span class="sxs-lookup"><span data-stu-id="549dd-102">How to Update an Assembly</span></span>
<span data-ttu-id="549dd-103">本主题介绍如何更新的程序集和程序集部署到使用 Visual Studio 2010 的应用程序的版本。</span><span class="sxs-lookup"><span data-stu-id="549dd-103">This topic describes how to update the version of an assembly and the application that an assembly is deployed to using Visual Studio 2010.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="549dd-104">如果你使用新版本进行更新程序集，你不需要重新启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="549dd-104">If you are updating an assembly with a new version, you do not need to restart the application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="549dd-105">必要條件</span><span class="sxs-lookup"><span data-stu-id="549dd-105">Prerequisites</span></span>  
 <span data-ttu-id="549dd-106">若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="549dd-106">To perform the procedures in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span>  
  
## <a name="updating-an-assembly"></a><span data-ttu-id="549dd-107">更新程序集</span><span class="sxs-lookup"><span data-stu-id="549dd-107">Updating an Assembly</span></span>  
  
#### <a name="to-increment-the-version-number-of-an-assembly"></a><span data-ttu-id="549dd-108">若要增加程序集的版本号</span><span class="sxs-lookup"><span data-stu-id="549dd-108">To increment the version number of an assembly</span></span>  
  
1.  <span data-ttu-id="549dd-109">在解决方案资源管理器，右键单击 BizTalk 项目，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="549dd-109">In Solution Explorer, right-click the BizTalk project, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="549dd-110">在**项目设计器**，单击**应用程序**选项卡。</span><span class="sxs-lookup"><span data-stu-id="549dd-110">In the **Project Designer**, click the **Application** tab.</span></span>  
  
3.  <span data-ttu-id="549dd-111">在右窗格中，单击**程序集信息**。</span><span class="sxs-lookup"><span data-stu-id="549dd-111">In the right pane, click **Assembly Information**.</span></span>  
  
4.  <span data-ttu-id="549dd-112">在**程序集信息**对话框框中，为指定值**程序集版本**字段以增加程序集版本号。</span><span class="sxs-lookup"><span data-stu-id="549dd-112">In the **Assembly Information** dialog box, specify values for the **Assembly Version** field to increase the assembly version number.</span></span> <span data-ttu-id="549dd-113">应该只递增主版本号或次版本号。</span><span class="sxs-lookup"><span data-stu-id="549dd-113">You should increase only the major or minor version number.</span></span> <span data-ttu-id="549dd-114">主版本号是序列中的第一个数字 (***n***.0.0.0); 的次版本号是序列中的第二个数字 (0。***n*** .0.0)。</span><span class="sxs-lookup"><span data-stu-id="549dd-114">The major version number is the first digit in the sequence (***n***.0.0.0); the minor version number is the second digit in the sequence (0.***n***.0.0).</span></span> <span data-ttu-id="549dd-115">BizTalk Server 将无法识别序列，如 0.0 中更高版本的版本编号更改。 ***n*** .0 或 0.0.0。***n***.</span><span class="sxs-lookup"><span data-stu-id="549dd-115">BizTalk Server will not recognize a version number change that is later in the sequence, such as 0.0.***n***.0 or 0.0.0.***n***.</span></span>  
  
5.  <span data-ttu-id="549dd-116">单击 **确定** 关闭 **程序集信息** 对话框。</span><span class="sxs-lookup"><span data-stu-id="549dd-116">Click **OK** to close the **Assembly Information** dialog box.</span></span>  
  
6.  <span data-ttu-id="549dd-117">保存项目。</span><span class="sxs-lookup"><span data-stu-id="549dd-117">Save the project.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="549dd-118">使用管道设计器和 BizTalk 浏览器对象模型，可以避免在递增程序集版本时出现架构冲突。</span><span class="sxs-lookup"><span data-stu-id="549dd-118">Use the Pipeline Designer and BizTalk Explorer Object Model to avoid schema collisions when incrementing assembly versions.</span></span>  
  
#### <a name="to-change-the-application-that-an-assembly-is-deployed-to"></a><span data-ttu-id="549dd-119">若要更改的应用程序程序集部署到</span><span class="sxs-lookup"><span data-stu-id="549dd-119">To change the application that an assembly is deployed to</span></span>  
  
1.  <span data-ttu-id="549dd-120">在解决方案资源管理器，右键单击 BizTalk 项目，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="549dd-120">In Solution Explorer, right-click the BizTalk project, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="549dd-121">在**项目设计器**，单击**部署**选项卡。</span><span class="sxs-lookup"><span data-stu-id="549dd-121">In the **Project Designer**, click the **Deployment** tab.</span></span>  
  
3.  <span data-ttu-id="549dd-122">在右窗格中，指定中的应用程序名称**应用程序名称**字段。</span><span class="sxs-lookup"><span data-stu-id="549dd-122">In the right pane, specify the application name in the **Application Name** field.</span></span>  
  
4.  <span data-ttu-id="549dd-123">确保**安装到全局程序集缓存**属性设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="549dd-123">Ensure that the **Install to Global Assembly Cache** property is set to **True**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="549dd-124">在您部署该解决方案时，这些程序集将部署到新应用程序中并安装在 GAC 中。</span><span class="sxs-lookup"><span data-stu-id="549dd-124">When you deploy the solution, the assemblies will be deployed into the new application and installed in the GAC.</span></span>