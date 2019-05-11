---
title: 如何将跟踪的消息复制到 BizTalk 跟踪数据库 |Microsoft Docs
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
ms.openlocfilehash: 0db85ded3ae545ebc0a4648d6324515484765d01
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340133"
---
# <a name="how-to-copy-tracked-messages-into-the-biztalk-tracking-database"></a><span data-ttu-id="f91ea-102">如何将跟踪的消息复制到 BizTalk 跟踪数据库</span><span class="sxs-lookup"><span data-stu-id="f91ea-102">How to Copy Tracked Messages into the BizTalk Tracking Database</span></span>
<span data-ttu-id="f91ea-103">存档和清除进程可能会访问和/或更新其他的 SQL server 中的数据库，因此必须设置所涉及的 SQL Server 实例之间的链接服务器。</span><span class="sxs-lookup"><span data-stu-id="f91ea-103">The archiving and purging process potentially accesses and/or updates databases in different SQL servers, so you must set up linked servers between the involved SQL Server instances.</span></span> <span data-ttu-id="f91ea-104">直接将跟踪的消息从 BizTalk MessageBox (BizTalkMsgBoxDb) 数据库服务器复制到 BizTalk 跟踪 (BizTalkDTADb) 数据库使用链接的服务器。</span><span class="sxs-lookup"><span data-stu-id="f91ea-104">You can directly copy tracked messages from the BizTalk MessageBox (BizTalkMsgBoxDb) database server to your BizTalk Tracking (BizTalkDTADb) database using a linked server.</span></span> <span data-ttu-id="f91ea-105">必须设置之间的链接服务器：</span><span class="sxs-lookup"><span data-stu-id="f91ea-105">You must set up linked servers between:</span></span>  
  
-   <span data-ttu-id="f91ea-106">每个 BizTalk MessageBox (BizTalkMsgBoxDb) 数据库和 BizTalk 跟踪 (BizTalkDTADb) 数据库。</span><span class="sxs-lookup"><span data-stu-id="f91ea-106">Each of your BizTalk MessageBox (BizTalkMsgBoxDb) databases and the BizTalk Tracking (BizTalkDTADb) database.</span></span>  
  
-   <span data-ttu-id="f91ea-107">BizTalk 跟踪 (BizTalkDTADb) 数据库和用于存档验证的验证服务器。</span><span class="sxs-lookup"><span data-stu-id="f91ea-107">The BizTalk Tracking (BizTalkDTADb) database and the validating server for archive validation.</span></span>  
  
-   <span data-ttu-id="f91ea-108">承载 BizTalk MessageBox (BizTalkMsgBoxDb) 数据库的计算机上的 SQL Server 代理服务帐户必须在链接服务器上具有 BizTalk 跟踪 (BizTalkDTADb) 数据库的 db_datareader 和 db_datawriter 权限。</span><span class="sxs-lookup"><span data-stu-id="f91ea-108">The service accounts for the SQL Server Agent on the computer hosting the BizTalk MessageBox (BizTalkMsgBoxDb) database must have the db_datareader and db_datawriter permissions for the BizTalk Tracking (BizTalkDTADb) database on the linked server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f91ea-109">在 SQL Server 代理中，验证复制作业运行，未出现错误。</span><span class="sxs-lookup"><span data-stu-id="f91ea-109">In SQL Server Agent, verify that the copy job runs without errors.</span></span> <span data-ttu-id="f91ea-110">否则，错误可能会阻止数据移动到跟踪数据库。</span><span class="sxs-lookup"><span data-stu-id="f91ea-110">Otherwise, errors might prevent data from being moved to the tracking database.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f91ea-111">先决条件</span><span class="sxs-lookup"><span data-stu-id="f91ea-111">Prerequisites</span></span>  
 <span data-ttu-id="f91ea-112">您必须是 SQL Server sysadmin 固定服务器角色的成员才能执行此过程的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="f91ea-112">You must be logged on with an account that is a member of the SQL Server sysadmin fixed server role to perform this procedure.</span></span>  
  
### <a name="to-copy-tracked-messages-into-the-biztalk-tracking-database-sql-server-2008"></a><span data-ttu-id="f91ea-113">若要将跟踪的消息复制到 BizTalk 跟踪数据库 (SQL Server 2008)</span><span class="sxs-lookup"><span data-stu-id="f91ea-113">To copy tracked messages into the BizTalk Tracking database (SQL Server 2008)</span></span>  
  
1.  <span data-ttu-id="f91ea-114">单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 R2**，然后单击**SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="f91ea-114">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="f91ea-115">在中**连接到服务器**对话框中，指定 BizTalk 跟踪 (BizTalkDTADb) 数据库所在的 SQL 服务器和相应的验证类型的名称，然后单击**Connect**到连接到相应的 SQL server。</span><span class="sxs-lookup"><span data-stu-id="f91ea-115">In the **Connect to Server** dialog box, specify the name of the SQL server where the BizTalk Tracking (BizTalkDTADb) database resides and the appropriate authentication type, and then click **Connect** to connect to the appropriate SQL server.</span></span>  
  
3.  <span data-ttu-id="f91ea-116">在中**Microsoft SQL Server Management Studio**，双击**SQL Server 代理**，然后单击**作业**。</span><span class="sxs-lookup"><span data-stu-id="f91ea-116">In **Microsoft SQL Server Management Studio**, double-click **SQL Server Agent**, and then click **Jobs**.</span></span>  
  
4.  <span data-ttu-id="f91ea-117">在细节窗格中，右键单击**TrackedMessages_Copy_BizTalkMsgBoxDb**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="f91ea-117">In the details pane, right-click **TrackedMessages_Copy_BizTalkMsgBoxDb**, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="f91ea-118">在中**作业属性-TrackedMessages_Copy_BizTalkMsgBoxDb**对话框中的**选择页**，单击**步骤**。</span><span class="sxs-lookup"><span data-stu-id="f91ea-118">In the **Job Properties - TrackedMessages_Copy_BizTalkMsgBoxDb** dialog box, under **Select a page**, click **Steps**.</span></span>  
  
6.  <span data-ttu-id="f91ea-119">下**作业步骤列表**，单击**清除**，然后单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="f91ea-119">Under **Job step list**, click **Purge**, and then click **Edit**.</span></span>  
  
7.  <span data-ttu-id="f91ea-120">在中**命令**框中，编辑跟踪服务器和数据库名称参数，根据需要，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="f91ea-120">In the **Command** box, edit the tracking server and database names parameters as appropriate, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="f91ea-121">上**作业属性-TrackedMessages_Copy_BizTalkMsgBoxDb**对话框中的**选择页**，单击**常规**，选择**已启用**复选框，然后依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="f91ea-121">On the **Job Properties - TrackedMessages_Copy_BizTalkMsgBoxDb** dialog box, under **Select a page**, click **General**,select the **Enabled** check box, and then click **OK**.</span></span>  
  
     <span data-ttu-id="f91ea-122">消息将从 BizTalk MessageBox (BizTalkMsgBoxDb) 复制到 BizTalk 跟踪 (BizTalkDTADb) 数据库。</span><span class="sxs-lookup"><span data-stu-id="f91ea-122">The messages will be copied from the BizTalk MessageBox (BizTalkMsgBoxDb) to the BizTalk Tracking (BizTalkDTADb) database.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f91ea-123">如果添加新的 MessageBox 数据库，需要为新的 MessageBox 数据库再次执行此过程。</span><span class="sxs-lookup"><span data-stu-id="f91ea-123">If you add a new MessageBox database, you will need to perform this procedure again for the new MessageBox database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f91ea-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="f91ea-124">See Also</span></span>  
 [<span data-ttu-id="f91ea-125">存档和清除 BizTalk 跟踪数据库</span><span class="sxs-lookup"><span data-stu-id="f91ea-125">Archiving and Purging the BizTalk Tracking Database</span></span>](../core/archiving-and-purging-the-biztalk-tracking-database.md)