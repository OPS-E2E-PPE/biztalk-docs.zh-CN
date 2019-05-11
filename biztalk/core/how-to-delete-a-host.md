---
title: 删除主机 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e3df8719-27cb-4010-82e3-68226ab74b17
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 351311d526500529c293fffbd400a5c1d317ed16
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385389"
---
# <a name="delete-a-host"></a><span data-ttu-id="3fd91-102">删除主机</span><span class="sxs-lookup"><span data-stu-id="3fd91-102">Delete a Host</span></span>
<span data-ttu-id="3fd91-103">可以删除仅在下列情况中的主机：</span><span class="sxs-lookup"><span data-stu-id="3fd91-103">You can delete a host only in the following circumstances:</span></span>  

- <span data-ttu-id="3fd91-104">它不是默认主机。</span><span class="sxs-lookup"><span data-stu-id="3fd91-104">It is not the default host.</span></span>  

- <span data-ttu-id="3fd91-105">它不进行主机跟踪的唯一主机。</span><span class="sxs-lookup"><span data-stu-id="3fd91-105">It is not the only host that is performing host tracking.</span></span>  

- <span data-ttu-id="3fd91-106">它不承载任何适配器处理程序。</span><span class="sxs-lookup"><span data-stu-id="3fd91-106">It is not hosting any adapter handlers.</span></span>  

- <span data-ttu-id="3fd91-107">它有没有已登记的业务流程。</span><span class="sxs-lookup"><span data-stu-id="3fd91-107">It has no enlisted orchestrations.</span></span>  

- <span data-ttu-id="3fd91-108">没有已启动的主机的实例。</span><span class="sxs-lookup"><span data-stu-id="3fd91-108">There are no started instances of the host.</span></span>  

- <span data-ttu-id="3fd91-109">如果主机未群集化。</span><span class="sxs-lookup"><span data-stu-id="3fd91-109">If the host is not clustered.</span></span>  

  <span data-ttu-id="3fd91-110">有关主机的详细信息，请参阅[主机](../core/hosts.md)。</span><span class="sxs-lookup"><span data-stu-id="3fd91-110">For more information about hosts, see [Hosts](../core/hosts.md).</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="3fd91-111">先决条件</span><span class="sxs-lookup"><span data-stu-id="3fd91-111">Prerequisites</span></span>  
 <span data-ttu-id="3fd91-112">必须具有以下的用户权限，才能创建主机、 修改主机属性和删除主机：</span><span class="sxs-lookup"><span data-stu-id="3fd91-112">You must have the following user rights to create hosts, modify host properties, and delete hosts:</span></span>  

-   <span data-ttu-id="3fd91-113">必须是 BizTalk Server Administrators 组的成员。</span><span class="sxs-lookup"><span data-stu-id="3fd91-113">You must be a member of the BizTalk Server Administrators group.</span></span>  

-   <span data-ttu-id="3fd91-114">SQL Server 中，必须具有以下权限：</span><span class="sxs-lookup"><span data-stu-id="3fd91-114">You must have the following rights in SQL Server:</span></span>  

    -   <span data-ttu-id="3fd91-115">您必须是 SQL Server 管理员或在 BizTalk 跟踪数据库 (BizTalk DTADb)、 MessageBox (BizTalkMsgBoxDb) 数据库和 BAM 主导入数据库 （中的 db_owner 或 db_securityadmin 的 SQL Server 数据库角色的成员BAMPrimaryImport)。</span><span class="sxs-lookup"><span data-stu-id="3fd91-115">You must be either a SQL Server administrator, or a member of the db_owner or db_securityadmin SQL Server database roles in the BizTalk Tracking database (BizTalk DTADb), MessageBox databases (BizTalkMsgBoxDb), and the BAM Primary Import database (BAMPrimaryImport).</span></span>  

    -   <span data-ttu-id="3fd91-116">其中有 MessageBox 数据库或所有 MessageBox 数据库的 db_owner 或 db_ddladmin SQL Server 角色的成员，您必须是所有计算机上的 sysadmin SQL Server 角色的成员。</span><span class="sxs-lookup"><span data-stu-id="3fd91-116">You must be a member of the sysadmin SQL Server role on all the computers where there are MessageBox databases, or a member of the db_owner or db_ddladmin SQL Server role for all the MessageBox databases.</span></span>  

## <a name="steps"></a><span data-ttu-id="3fd91-117">步骤</span><span class="sxs-lookup"><span data-stu-id="3fd91-117">Steps</span></span> 

1. <span data-ttu-id="3fd91-118">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="3fd91-118">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="3fd91-119">在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开 BizTalk 组，单击**平台设置**，然后单击**主机**。</span><span class="sxs-lookup"><span data-stu-id="3fd91-119">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, click **Platform Settings**, and then click **Hosts**.</span></span>  

3. <span data-ttu-id="3fd91-120">在细节窗格中，右键单击你想要删除，然后单击的主机**删除**。</span><span class="sxs-lookup"><span data-stu-id="3fd91-120">In the details pane, right-click the host you want to delete, and then click **Delete**.</span></span>  

4. <span data-ttu-id="3fd91-121">在中**确认主机删除**对话框中，单击**是**。</span><span class="sxs-lookup"><span data-stu-id="3fd91-121">In the **Confirm host delete** dialog box, click **Yes**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="3fd91-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="3fd91-122">See Also</span></span>  
- [<span data-ttu-id="3fd91-123">管理 BizTalk 主机和主机实例</span><span class="sxs-lookup"><span data-stu-id="3fd91-123">Managing BizTalk Hosts and Host Instances</span></span>](../core/managing-biztalk-hosts-and-host-instances.md)   
- [<span data-ttu-id="3fd91-124">如何创建新的主机</span><span class="sxs-lookup"><span data-stu-id="3fd91-124">How to Create a New Host</span></span>](../core/how-to-create-a-new-host.md)   
- [<span data-ttu-id="3fd91-125">如何修改主机属性</span><span class="sxs-lookup"><span data-stu-id="3fd91-125">How to Modify Host Properties</span></span>](../core/how-to-modify-host-properties.md)   
- <span data-ttu-id="3fd91-126">**MSBTS_Host (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="3fd91-126">**MSBTS_Host (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
