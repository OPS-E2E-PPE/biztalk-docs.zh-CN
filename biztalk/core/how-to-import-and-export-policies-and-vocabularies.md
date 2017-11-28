---
title: "如何导入和导出策略和词汇 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- policies, exporting
- Rule Engine Deployment Wizard
- policies, importing
- vocabularies, exporting
- vocabularies, importing
ms.assetid: c427f686-5908-4f72-9e72-46a5497274ac
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17ba7cd8a9fc5d28d1b718e9a47ad6cf2f448ec7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-import-and-export-policies-and-vocabularies"></a><span data-ttu-id="04bdb-102">如何导入和导出策略及词汇</span><span class="sxs-lookup"><span data-stu-id="04bdb-102">How to Import and Export Policies and Vocabularies</span></span>
<span data-ttu-id="04bdb-103">可以使用规则引擎部署向导导入或导出策略或词汇。</span><span class="sxs-lookup"><span data-stu-id="04bdb-103">You can use the Rules Engine Deployment Wizard to import or export a policy or vocabulary.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="04bdb-104">必须首先导入策略或词汇使用的所有词汇，否则将出现错误。</span><span class="sxs-lookup"><span data-stu-id="04bdb-104">All vocabularies used by a policy or vocabulary must be imported first or you will get an error.</span></span>  
  
### <a name="to-import-or-export-a-policy-or-vocabulary"></a><span data-ttu-id="04bdb-105">导入或导出策略或词汇</span><span class="sxs-lookup"><span data-stu-id="04bdb-105">To import or export a policy or vocabulary</span></span>  
  
1.  <span data-ttu-id="04bdb-106">单击**启动**，指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**业务规则引擎部署向导**。</span><span class="sxs-lookup"><span data-stu-id="04bdb-106">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **Business Rules Engine Deployment Wizard**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="04bdb-107">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="04bdb-107">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="04bdb-108">要执行此操作，右键单击该应用程序，，然后选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="04bdb-108">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="04bdb-109">在欢迎页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="04bdb-109">On the welcome page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="04bdb-110">上**部署任务**页上，选择**导出策略/词汇文件从数据库**或**导入并将其从文件发布到数据库的策略/词汇**，，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="04bdb-110">On the **Deployment Task** page, select either **Export Policy/Vocabulary to file from database** or **Import and publish Policy/Vocabulary to database from file**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="04bdb-111">上**策略存储区**页上，从下拉列表中，选择可用的 SQL Server 计算机和数据库，，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="04bdb-111">On the **Policy Store** page, from the drop-down lists, select an available SQL Server computer and database, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="04bdb-112">上**导出策略/词汇**页上，执行以下操作，，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="04bdb-112">On the **Export Policy/Vocabulary** page, do the following, and then click **Next**.</span></span>  
  
    1.  <span data-ttu-id="04bdb-113">选择**策略**或**词汇**具体取决于你想要导出/导入。</span><span class="sxs-lookup"><span data-stu-id="04bdb-113">Select **Policy** or **Vocabulary** depending on what you want to export/import.</span></span>  
  
    2.  <span data-ttu-id="04bdb-114">从**策略/词汇**下拉列表中，选择所需的策略/词汇。</span><span class="sxs-lookup"><span data-stu-id="04bdb-114">From the **Policy/Vocabulary** drop-down list, select the desired policy/vocabulary.</span></span>  
  
    3.  <span data-ttu-id="04bdb-115">单击**浏览**选择定义文件。</span><span class="sxs-lookup"><span data-stu-id="04bdb-115">Click **Browse** to select the definition file.</span></span>  
  
6.  <span data-ttu-id="04bdb-116">查看服务器、 数据库和策略或词汇信息，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="04bdb-116">Review the server, database, and policy or vocabulary information, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="04bdb-117">完成导入或导出后，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="04bdb-117">After the import or export is completed, click **Next**.</span></span>  
  
8.  <span data-ttu-id="04bdb-118">查看导入或导出的完成状态，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="04bdb-118">Review the completion status of the import or export, and then click **Finish**.</span></span>