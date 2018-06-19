---
title: 配置和查看审核日志 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c725bf04-d59f-42c1-b327-b4268421689c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03c88e0a67a393b7ddc35ee8865d99d0299d41f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289837"
---
# <a name="configuring-and-viewing-audit-logs"></a><span data-ttu-id="c5bf2-102">配置和查看审核日志</span><span class="sxs-lookup"><span data-stu-id="c5bf2-102">Configuring and Viewing Audit Logs</span></span>
<span data-ttu-id="c5bf2-103">ESB 管理门户维护帮助你监视使用情况和跟踪问题的操作的审核日志。</span><span class="sxs-lookup"><span data-stu-id="c5bf2-103">The ESB Management Portal maintains an audit log of actions that help you to monitor usage and track problems.</span></span> <span data-ttu-id="c5bf2-104">管理员可以指定该门户将写入审核日志的事件。</span><span class="sxs-lookup"><span data-stu-id="c5bf2-104">Administrators can specify which events the portal will write to the audit log.</span></span>  
  
### <a name="to-view-the-audit-logs-for-the-portal"></a><span data-ttu-id="c5bf2-105">若要查看门户的审核日志</span><span class="sxs-lookup"><span data-stu-id="c5bf2-105">To view the audit logs for the portal</span></span>  
  
1.  <span data-ttu-id="c5bf2-106">指向**管理员**在门户的主菜单上，选项卡，然后单击**管理审核日志**以打开[审核日志页](../esb-toolkit/audit-log-page.md)。</span><span class="sxs-lookup"><span data-stu-id="c5bf2-106">Point to the **Admin** tab on the portal main menu, and then click **Manage Audit Log** to open the [Audit Log Page](../esb-toolkit/audit-log-page.md).</span></span>  
  
2.  <span data-ttu-id="c5bf2-107">若要查看的重新提交详细信息和重新提交消息的原始消息，请单击要打开的审核日志-消息查看器页列表中的消息的标识符。</span><span class="sxs-lookup"><span data-stu-id="c5bf2-107">To see the resubmission details and the original message for resubmitted messages, click the identifier of a message in the list to open the Audit Log – Message Viewer page.</span></span>  
  
### <a name="to-configure-the-auditing-settings-for-the-portal"></a><span data-ttu-id="c5bf2-108">若要配置门户的审核设置</span><span class="sxs-lookup"><span data-stu-id="c5bf2-108">To configure the auditing settings for the portal</span></span>  
  
1.  <span data-ttu-id="c5bf2-109">确保您登录到门户使用的 BizTalk Server 管理员帐户 （其中门户管理员自动成员身份组） 成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="c5bf2-109">Ensure that you log on to the portal using an account that is a member of the BizTalk Server Administrators account group (of which portal administrators are automatically a member).</span></span>  
  
2.  <span data-ttu-id="c5bf2-110">指向**管理员**在门户的主菜单上，选项卡，然后单击**错误设置**以打开门户[错误设置页](../esb-toolkit/fault-settings-page.md)。</span><span class="sxs-lookup"><span data-stu-id="c5bf2-110">Point to the **Admin** tab on the portal main menu, and then click **Fault Settings** to open the portal [Fault Settings Page](../esb-toolkit/fault-settings-page.md).</span></span>  
  
3.  <span data-ttu-id="c5bf2-111">若要更改的审核选项，选择中的复选框**AuditOptions**部分为你要审核每个事件。</span><span class="sxs-lookup"><span data-stu-id="c5bf2-111">To change the auditing options, select the check boxes in the **AuditOptions** section for each event you want to audit.</span></span> <span data-ttu-id="c5bf2-112">当重新提交错误时，可用的事件将非常保存修改后的设置，编辑和失败后成功重新提交错误。</span><span class="sxs-lookup"><span data-stu-id="c5bf2-112">The available events are the saving of modified settings, successful resubmission of a fault after editing, and failure when resubmitting a fault.</span></span>