---
title: 如何将跟踪的消息复制到跟踪数据库 BizTalk |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, copying between servers
- MessageBox database, Tracking database
- Tracking database, linking servers
- MessageBox database, copying messages
- linking, servers
- Tracking database, archiving
- archiving [Tracking database], linking servers
- Tracking database, MessageBox database
- Tracking database, copying messages
- archiving [Tracking database], MessageBox database
- MessageBox database, linking servers
- MessageBox database, archiving
ms.assetid: 369e972a-efbe-4ad5-a68f-aa3bbfb9ad54
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23aaa8e3bea3405d51a18da1778d420550ad4584
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2018
---
# <a name="how-to-copy-tracked-messages-into-the-biztalk-tracking-database"></a><span data-ttu-id="8ecc4-102">如何将跟踪的消息复制到跟踪数据库 BizTalk</span><span class="sxs-lookup"><span data-stu-id="8ecc4-102">How to Copy Tracked Messages into the BizTalk Tracking Database</span></span>
<span data-ttu-id="8ecc4-103">存档和清除进程可能会访问和/或更新其他 SQL Server 中的数据库，因此必须在所涉及的 SQL Server 实例之间设置链接服务器。</span><span class="sxs-lookup"><span data-stu-id="8ecc4-103">The archiving and purging process potentially accesses and/or updates databases in different SQL servers, so you must set up linked servers between the involved SQL Server instances.</span></span> <span data-ttu-id="8ecc4-104">可以使用链接服务器直接将跟踪的消息从 BizTalk MessageBox (BizTalkMsgBoxDb) 数据库服务器复制到 BizTalk 跟踪 (BizTalkDTADb) 数据库中。</span><span class="sxs-lookup"><span data-stu-id="8ecc4-104">You can directly copy tracked messages from the BizTalk MessageBox (BizTalkMsgBoxDb) database server to your BizTalk Tracking (BizTalkDTADb) database using a linked server.</span></span> <span data-ttu-id="8ecc4-105">必须在以下项之间设置链接服务器：</span><span class="sxs-lookup"><span data-stu-id="8ecc4-105">You must set up linked servers between:</span></span>  
  
-   <span data-ttu-id="8ecc4-106">每个 BizTalk MessageBox (BizTalkMsgBoxDb) 数据库以及 BizTalk 跟踪 (BizTalkDTADb) 数据库。</span><span class="sxs-lookup"><span data-stu-id="8ecc4-106">Each of your BizTalk MessageBox (BizTalkMsgBoxDb) databases and the BizTalk Tracking (BizTalkDTADb) database.</span></span>  
  
-   <span data-ttu-id="8ecc4-107">BizTalk 跟踪 (BizTalkDTADb) 数据库以及用于存档验证的验证服务器。</span><span class="sxs-lookup"><span data-stu-id="8ecc4-107">The BizTalk Tracking (BizTalkDTADb) database and the validating server for archive validation.</span></span>  
  
-   <span data-ttu-id="8ecc4-108">BizTalk MessageBox (BizTalkMsgBoxDb) 数据库的宿主计算机上的 SQL Server 代理的服务帐户必须对链接服务器上的 BizTalk 跟踪 (BizTalkDTADb) 数据库具有 db_datareader 和 db_datawriter 权限。</span><span class="sxs-lookup"><span data-stu-id="8ecc4-108">The service accounts for the SQL Server Agent on the computer hosting the BizTalk MessageBox (BizTalkMsgBoxDb) database must have the db_datareader and db_datawriter permissions for the BizTalk Tracking (BizTalkDTADb) database on the linked server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8ecc4-109">在 SQL Server 代理中，验证复制作业能够正常运行，而不会产生任何错误。</span><span class="sxs-lookup"><span data-stu-id="8ecc4-109">In SQL Server Agent, verify that the copy job runs without errors.</span></span> <span data-ttu-id="8ecc4-110">否则，错误可能会阻止将数据移动到跟踪数据库中。</span><span class="sxs-lookup"><span data-stu-id="8ecc4-110">Otherwise, errors might prevent data from being moved to the tracking database.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8ecc4-111">先决条件</span><span class="sxs-lookup"><span data-stu-id="8ecc4-111">Prerequisites</span></span>  
 <span data-ttu-id="8ecc4-112">若要执行此过程，必须以 SQL Server sysadmin 固定服务器角色成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="8ecc4-112">You must be logged on with an account that is a member of the SQL Server sysadmin fixed server role to perform this procedure.</span></span>  
  
### <a name="to-copy-tracked-messages-into-the-biztalk-tracking-database-sql-server-2008"></a><span data-ttu-id="8ecc4-113">若要将跟踪的消息复制到 BizTalk 跟踪数据库 (SQL Server 2008)</span><span class="sxs-lookup"><span data-stu-id="8ecc4-113">To copy tracked messages into the BizTalk Tracking database (SQL Server 2008)</span></span>  
  
1.  <span data-ttu-id="8ecc4-114">单击 **启动**, ，单击 **所有程序**, ，单击 **Microsoft SQL Server 2008 R2**, ，然后单击 **SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="8ecc4-114">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="8ecc4-115">在 **连接到服务器** 对话框中，指定 BizTalk 跟踪 (BizTalkDTADb) 数据库所在的 SQL server 和适当的身份验证类型的名称，然后单击 **连接** 以连接到相应的 SQL server。</span><span class="sxs-lookup"><span data-stu-id="8ecc4-115">In the **Connect to Server** dialog box, specify the name of the SQL server where the BizTalk Tracking (BizTalkDTADb) database resides and the appropriate authentication type, and then click **Connect** to connect to the appropriate SQL server.</span></span>  
  
3.  <span data-ttu-id="8ecc4-116">在 **Microsoft SQL Server Management Studio**, ，双击 **SQL Server 代理**, ，然后单击 **作业**。</span><span class="sxs-lookup"><span data-stu-id="8ecc4-116">In **Microsoft SQL Server Management Studio**, double-click **SQL Server Agent**, and then click **Jobs**.</span></span>  
  
4.  <span data-ttu-id="8ecc4-117">在细节窗格中，右键单击 **TrackedMessages_Copy_BizTalkMsgBoxDb**, ，然后单击 **属性**。</span><span class="sxs-lookup"><span data-stu-id="8ecc4-117">In the details pane, right-click **TrackedMessages_Copy_BizTalkMsgBoxDb**, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="8ecc4-118">在 **作业属性-TrackedMessages_Copy_BizTalkMsgBoxDb** 对话框中，在 **选择页**, ，单击 **步骤**。</span><span class="sxs-lookup"><span data-stu-id="8ecc4-118">In the **Job Properties - TrackedMessages_Copy_BizTalkMsgBoxDb** dialog box, under **Select a page**, click **Steps**.</span></span>  
  
6.  <span data-ttu-id="8ecc4-119">下 **作业步骤列表**, ，单击 **清除**, ，然后单击 **编辑**。</span><span class="sxs-lookup"><span data-stu-id="8ecc4-119">Under **Job step list**, click **Purge**, and then click **Edit**.</span></span>  
  
7.  <span data-ttu-id="8ecc4-120">在 **命令** 框中，编辑跟踪服务器和数据库名称参数视情况而定，然后单击 **确定**。</span><span class="sxs-lookup"><span data-stu-id="8ecc4-120">In the **Command** box, edit the tracking server and database names parameters as appropriate, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="8ecc4-121">上 **作业属性-TrackedMessages_Copy_BizTalkMsgBoxDb** 对话框中，在 **选择页**, ，单击 **常规**,，选择 **已启用** 复选框，并依次 **确定**。</span><span class="sxs-lookup"><span data-stu-id="8ecc4-121">On the **Job Properties - TrackedMessages_Copy_BizTalkMsgBoxDb** dialog box, under **Select a page**, click **General**,select the **Enabled** check box, and then click **OK**.</span></span>  
  
     <span data-ttu-id="8ecc4-122">消息将从 BizTalk MessageBox 数据库 (BizTalkMsgBoxDb) 复制到 BizTalk 跟踪数据库 (BizTalkDTADb)。</span><span class="sxs-lookup"><span data-stu-id="8ecc4-122">The messages will be copied from the BizTalk MessageBox (BizTalkMsgBoxDb) to the BizTalk Tracking (BizTalkDTADb) database.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8ecc4-123">如果添加新的 MessageBox 数据库，将需要为新的 MessageBox 数据库再执行一次此过程。</span><span class="sxs-lookup"><span data-stu-id="8ecc4-123">If you add a new MessageBox database, you will need to perform this procedure again for the new MessageBox database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ecc4-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8ecc4-124">See Also</span></span>  
 [<span data-ttu-id="8ecc4-125">存档和清除 BizTalk 跟踪数据库</span><span class="sxs-lookup"><span data-stu-id="8ecc4-125">Archiving and Purging the BizTalk Tracking Database</span></span>](../core/archiving-and-purging-the-biztalk-tracking-database.md)