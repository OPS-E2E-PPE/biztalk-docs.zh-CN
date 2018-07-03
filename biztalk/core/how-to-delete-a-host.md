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
ms.openlocfilehash: e65c2997fa19ed961515285ce04f51acc4c196e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995278"
---
# <a name="delete-a-host"></a><span data-ttu-id="c9ba7-102">删除主机</span><span class="sxs-lookup"><span data-stu-id="c9ba7-102">Delete a Host</span></span>
<span data-ttu-id="c9ba7-103">只有在下列情况下才能删除主机：</span><span class="sxs-lookup"><span data-stu-id="c9ba7-103">You can delete a host only in the following circumstances:</span></span>  

- <span data-ttu-id="c9ba7-104">该主机不是默认主机。</span><span class="sxs-lookup"><span data-stu-id="c9ba7-104">It is not the default host.</span></span>  

- <span data-ttu-id="c9ba7-105">该主机不是进行主机跟踪的唯一主机。</span><span class="sxs-lookup"><span data-stu-id="c9ba7-105">It is not the only host that is performing host tracking.</span></span>  

- <span data-ttu-id="c9ba7-106">该主机未用作任何适配器处理程序的宿主。</span><span class="sxs-lookup"><span data-stu-id="c9ba7-106">It is not hosting any adapter handlers.</span></span>  

- <span data-ttu-id="c9ba7-107">该主机没有已登记的业务流程。</span><span class="sxs-lookup"><span data-stu-id="c9ba7-107">It has no enlisted orchestrations.</span></span>  

- <span data-ttu-id="c9ba7-108">该主机没有已启动的实例。</span><span class="sxs-lookup"><span data-stu-id="c9ba7-108">There are no started instances of the host.</span></span>  

- <span data-ttu-id="c9ba7-109">未对该主机进行群集。</span><span class="sxs-lookup"><span data-stu-id="c9ba7-109">If the host is not clustered.</span></span>  

  <span data-ttu-id="c9ba7-110">有关主机的详细信息，请参阅[主机](../core/hosts.md)。</span><span class="sxs-lookup"><span data-stu-id="c9ba7-110">For more information about hosts, see [Hosts](../core/hosts.md).</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="c9ba7-111">必要條件</span><span class="sxs-lookup"><span data-stu-id="c9ba7-111">Prerequisites</span></span>  
 <span data-ttu-id="c9ba7-112">必须具有以下用户权限才能创建主机、修改主机属性和删除主机：</span><span class="sxs-lookup"><span data-stu-id="c9ba7-112">You must have the following user rights to create hosts, modify host properties, and delete hosts:</span></span>  

-   <span data-ttu-id="c9ba7-113">必须是 BizTalk Server Administrators 组的成员。</span><span class="sxs-lookup"><span data-stu-id="c9ba7-113">You must be a member of the BizTalk Server Administrators group.</span></span>  

-   <span data-ttu-id="c9ba7-114">必须在 SQL Server 中具有以下权限：</span><span class="sxs-lookup"><span data-stu-id="c9ba7-114">You must have the following rights in SQL Server:</span></span>  

    -   <span data-ttu-id="c9ba7-115">必须是 SQL Server 管理员，或者是 BizTalk 跟踪数据库 (BizTalk DTADb)、MessageBox 数据库 (BizTalkMsgBoxDb) 和 BAM 主导入数据库 (BAMPrimaryImport) 中的 db_owner 或 db_securityadmin SQL Server 数据库角色的成员。</span><span class="sxs-lookup"><span data-stu-id="c9ba7-115">You must be either a SQL Server administrator, or a member of the db_owner or db_securityadmin SQL Server database roles in the BizTalk Tracking database (BizTalk DTADb), MessageBox databases (BizTalkMsgBoxDb), and the BAM Primary Import database (BAMPrimaryImport).</span></span>  

    -   <span data-ttu-id="c9ba7-116">必须是 MessageBox 数据库所在的所有计算机上的 sysadmin SQL Server 角色的成员，或者是所有 MessageBox 数据库的 db_owner 或 db_ddladmin SQL Server 角色的成员。</span><span class="sxs-lookup"><span data-stu-id="c9ba7-116">You must be a member of the sysadmin SQL Server role on all the computers where there are MessageBox databases, or a member of the db_owner or db_ddladmin SQL Server role for all the MessageBox databases.</span></span>  

## <a name="steps"></a><span data-ttu-id="c9ba7-117">步骤</span><span class="sxs-lookup"><span data-stu-id="c9ba7-117">Steps</span></span> 

1. <span data-ttu-id="c9ba7-118">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="c9ba7-118">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="c9ba7-119">在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开 BizTalk 组，单击**平台设置**，然后单击**主机**。</span><span class="sxs-lookup"><span data-stu-id="c9ba7-119">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, click **Platform Settings**, and then click **Hosts**.</span></span>  

3. <span data-ttu-id="c9ba7-120">在细节窗格中，右键单击你想要删除，然后单击的主机**删除**。</span><span class="sxs-lookup"><span data-stu-id="c9ba7-120">In the details pane, right-click the host you want to delete, and then click **Delete**.</span></span>  

4. <span data-ttu-id="c9ba7-121">在中**确认主机删除**对话框中，单击**是**。</span><span class="sxs-lookup"><span data-stu-id="c9ba7-121">In the **Confirm host delete** dialog box, click **Yes**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="c9ba7-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="c9ba7-122">See Also</span></span>  
- [<span data-ttu-id="c9ba7-123">管理 BizTalk 主机和主机实例</span><span class="sxs-lookup"><span data-stu-id="c9ba7-123">Managing BizTalk Hosts and Host Instances</span></span>](../core/managing-biztalk-hosts-and-host-instances.md)   
- [<span data-ttu-id="c9ba7-124">如何创建新的主机</span><span class="sxs-lookup"><span data-stu-id="c9ba7-124">How to Create a New Host</span></span>](../core/how-to-create-a-new-host.md)   
- [<span data-ttu-id="c9ba7-125">如何修改主机属性</span><span class="sxs-lookup"><span data-stu-id="c9ba7-125">How to Modify Host Properties</span></span>](../core/how-to-modify-host-properties.md)   
- <span data-ttu-id="c9ba7-126">**MSBTS_Host (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="c9ba7-126">**MSBTS_Host (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
