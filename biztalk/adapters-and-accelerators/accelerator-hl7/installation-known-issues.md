---
title: "已知问题的安装 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b2f80ff9-b37c-49f8-8250-fcf3cec4c0fc
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf4e9197d2b3c448b4fd9cc42c0cdeb929917061
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="installation-known-issues"></a><span data-ttu-id="3f1d9-102">安装的已知问题</span><span class="sxs-lookup"><span data-stu-id="3f1d9-102">Installation known issues</span></span>
<span data-ttu-id="3f1d9-103">有用的信息来帮助你避免安装问题。</span><span class="sxs-lookup"><span data-stu-id="3f1d9-103">Useful information that may help you avoid installation problems.</span></span>  
  
## <a name="prerequisites-for-installing-btahl7"></a><span data-ttu-id="3f1d9-104">安装 BTAHL7 的先决条件</span><span class="sxs-lookup"><span data-stu-id="3f1d9-104">Prerequisites for installing BTAHL7</span></span>  
 <span data-ttu-id="3f1d9-105">安装的先决条件[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]如下：</span><span class="sxs-lookup"><span data-stu-id="3f1d9-105">The prerequisites for installing [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] include the following:</span></span>  
  
-   <span data-ttu-id="3f1d9-106">基本组件[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，包括企业单一登录 (SSO)、 组和运行时，应配置。</span><span class="sxs-lookup"><span data-stu-id="3f1d9-106">Basic components of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], including Enterprise Single Sign-On (SSO), Group, and Runtime, should be configured.</span></span>  
  
-   <span data-ttu-id="3f1d9-107">安装和配置 BTAHL7 用户必须是 BizTalk 管理员组的成员和存储 BTAHL7 数据的 SQL 服务器上的管理员组的成员。</span><span class="sxs-lookup"><span data-stu-id="3f1d9-107">The user installing and configuring BTAHL7 must be a member of the BizTalk Administrators group, and a member of the Administrators group on the SQL Server where the BTAHL7 data is stored.</span></span>
  
## <a name="sql-server-mixed-mode-not-supported"></a><span data-ttu-id="3f1d9-108">不支持的 SQL Server 混合的模式</span><span class="sxs-lookup"><span data-stu-id="3f1d9-108">SQL Server mixed mode not supported</span></span>  
<span data-ttu-id="3f1d9-109">[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]不在混合模式下支持 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="3f1d9-109">The [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] does not support SQL Server in mixed mode.</span></span>  
  
## <a name="repair-does-not-work-from-uninstallchange"></a><span data-ttu-id="3f1d9-110">修复卸载/更改中无法正常工作</span><span class="sxs-lookup"><span data-stu-id="3f1d9-110">Repair does not work from uninstall/change</span></span>  
<span data-ttu-id="3f1d9-111">如果启用了用户访问控制 (UAC)，并且你尝试使用控制面板修复安装，则修复失败。</span><span class="sxs-lookup"><span data-stu-id="3f1d9-111">If user access control (UAC) is enabled, and you try to repair your installation using the control panel, the repair fails.</span></span> 

<span data-ttu-id="3f1d9-112">Microsoft 建议你保留支持 UAC。</span><span class="sxs-lookup"><span data-stu-id="3f1d9-112">Microsoft recommends you keep UAC enabled.</span></span>

 <span data-ttu-id="3f1d9-113">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="3f1d9-113">**Resolution**</span></span>  
  
 <span data-ttu-id="3f1d9-114">运行[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]setup.exe，然后选择**修复**。</span><span class="sxs-lookup"><span data-stu-id="3f1d9-114">Run the [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] setup.exe, and then select **Repair**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f1d9-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3f1d9-115">See Also</span></span>  
[<span data-ttu-id="3f1d9-116">安装或升级 Microsoft BizTalk Accelerator for HL7</span><span class="sxs-lookup"><span data-stu-id="3f1d9-116">Install or upgrade Microsoft BizTalk Accelerator for HL7</span></span>](../../adapters-and-accelerators/accelerator-hl7/install-or-upgrade-microsoft-biztalk-accelerator-for-hl7.md)