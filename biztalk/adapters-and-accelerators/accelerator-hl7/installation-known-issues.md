---
title: 安装的已知问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b2f80ff9-b37c-49f8-8250-fcf3cec4c0fc
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c95a8de4437f2ae52c01f77fbfe6e4ff0d559d7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65300079"
---
# <a name="installation-known-issues"></a><span data-ttu-id="7cf0a-102">安装的已知问题</span><span class="sxs-lookup"><span data-stu-id="7cf0a-102">Installation known issues</span></span>
<span data-ttu-id="7cf0a-103">有用的信息可帮助你避免出现安装问题。</span><span class="sxs-lookup"><span data-stu-id="7cf0a-103">Useful information that may help you avoid installation problems.</span></span>  
  
## <a name="prerequisites-for-installing-btahl7"></a><span data-ttu-id="7cf0a-104">安装 BTAHL7 的先决条件</span><span class="sxs-lookup"><span data-stu-id="7cf0a-104">Prerequisites for installing BTAHL7</span></span>  
 <span data-ttu-id="7cf0a-105">安装的先决条件[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]包括以下：</span><span class="sxs-lookup"><span data-stu-id="7cf0a-105">The prerequisites for installing [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] include the following:</span></span>  
  
- <span data-ttu-id="7cf0a-106">基本组件[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]（包括企业单一登录 (SSO)、 组和运行时），应配置。</span><span class="sxs-lookup"><span data-stu-id="7cf0a-106">Basic components of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], including Enterprise Single Sign-On (SSO), Group, and Runtime, should be configured.</span></span>  
  
- <span data-ttu-id="7cf0a-107">安装和配置 BTAHL7 用户必须是 BizTalk Administrators 组的成员和 BTAHL7 数据的存储位置的 SQL Server 上管理员组的成员。</span><span class="sxs-lookup"><span data-stu-id="7cf0a-107">The user installing and configuring BTAHL7 must be a member of the BizTalk Administrators group, and a member of the Administrators group on the SQL Server where the BTAHL7 data is stored.</span></span>
  
## <a name="sql-server-mixed-mode-not-supported"></a><span data-ttu-id="7cf0a-108">不支持的 SQL Server 混合的模式</span><span class="sxs-lookup"><span data-stu-id="7cf0a-108">SQL Server mixed mode not supported</span></span>  
<span data-ttu-id="7cf0a-109">[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]不在混合模式下支持 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="7cf0a-109">The [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] does not support SQL Server in mixed mode.</span></span>  
  
## <a name="repair-does-not-work-from-uninstallchange"></a><span data-ttu-id="7cf0a-110">修复卸载/更改中无法正常工作</span><span class="sxs-lookup"><span data-stu-id="7cf0a-110">Repair does not work from uninstall/change</span></span>  
<span data-ttu-id="7cf0a-111">如果启用用户访问控制 (UAC)，并尝试使用控制面板修复安装，修复将失败。</span><span class="sxs-lookup"><span data-stu-id="7cf0a-111">If user access control (UAC) is enabled, and you try to repair your installation using the control panel, the repair fails.</span></span> 

<span data-ttu-id="7cf0a-112">Microsoft 建议您将在启用 UAC。</span><span class="sxs-lookup"><span data-stu-id="7cf0a-112">Microsoft recommends you keep UAC enabled.</span></span>

 <span data-ttu-id="7cf0a-113">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="7cf0a-113">**Resolution**</span></span>  
  
 <span data-ttu-id="7cf0a-114">运行[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]setup.exe，并选择**修复**。</span><span class="sxs-lookup"><span data-stu-id="7cf0a-114">Run the [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] setup.exe, and then select **Repair**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cf0a-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="7cf0a-115">See Also</span></span>  
[<span data-ttu-id="7cf0a-116">安装或升级 Microsoft BizTalk Accelerator for HL7</span><span class="sxs-lookup"><span data-stu-id="7cf0a-116">Install or upgrade Microsoft BizTalk Accelerator for HL7</span></span>](../../adapters-and-accelerators/accelerator-hl7/install-or-upgrade-microsoft-biztalk-accelerator-for-hl7.md)