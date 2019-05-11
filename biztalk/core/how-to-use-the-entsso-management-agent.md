---
title: 如何使用 ENTSSO 管理代理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9c89b494-db12-4d2a-a030-6acd34489cab
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5316fc279ea7dc0c29038ffefb1b16770bf6469
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383348"
---
# <a name="how-to-use-the-entsso-management-agent"></a><span data-ttu-id="8c678-102">如何使用 ENTSSO 管理代理</span><span class="sxs-lookup"><span data-stu-id="8c678-102">How to Use the ENTSSO Management Agent</span></span>
<span data-ttu-id="8c678-103">此版本的企业单一登录 (SSO) 包含管理代理 (MA) 的 Microsoft Identity Integration Server (MIIS)，其中将企业 SSO 与 MIIS 的帐户同步功能集成起来。</span><span class="sxs-lookup"><span data-stu-id="8c678-103">This version of Enterprise Single Sign-On (SSO) contains a Management Agent (MA) for Microsoft Identity Integration Server (MIIS), which integrates Enterprise SSO with the account synchronization capabilities of MIIS.</span></span> <span data-ttu-id="8c678-104">这样，MIIS 管理员来管理 SSO 数据库中的 SSO 映射。</span><span class="sxs-lookup"><span data-stu-id="8c678-104">This enables an MIIS administrator to manage SSO mappings in the SSO Database.</span></span>  
  
 <span data-ttu-id="8c678-105">在企业 SSO 之间创建映射的 Windows 域帐户 (*域名 \ 用户名*) 和外部凭据。</span><span class="sxs-lookup"><span data-stu-id="8c678-105">In Enterprise SSO, mappings are created between Windows Domain accounts (*domainname\username*) and external credentials.</span></span> <span data-ttu-id="8c678-106">如果为外部数据源具有 Active Directory 管理代理和管理代理 (示例：RACF MA)，可以使用企业 SSO MA (ENTSSO MA) 来管理 SSO 数据库中的映射。</span><span class="sxs-lookup"><span data-stu-id="8c678-106">If you have an Active Directory Management Agent, and the Management Agent for the external Data Source (example: RACF MA), you can use the Enterprise SSO MA (ENTSSO MA) to manage mappings in the SSO Database.</span></span> <span data-ttu-id="8c678-107">ENTSSO MA 是*基于呼叫的导出*仅管理代理。</span><span class="sxs-lookup"><span data-stu-id="8c678-107">ENTSSO MA is a *Call-Based Export* Management Agent only.</span></span>  
  
 <span data-ttu-id="8c678-108">在三个独立的部分中配置管理代理：</span><span class="sxs-lookup"><span data-stu-id="8c678-108">You configure the Management Agent in three separate parts:</span></span>  
  
- <span data-ttu-id="8c678-109">配置文件 (ENTSSO.xml)</span><span class="sxs-lookup"><span data-stu-id="8c678-109">A configuration file (ENTSSO.xml)</span></span>  
  
- <span data-ttu-id="8c678-110">MIIS 用户界面</span><span class="sxs-lookup"><span data-stu-id="8c678-110">The MIIS user interface</span></span>  
  
- <span data-ttu-id="8c678-111">ENTSSO 用户界面</span><span class="sxs-lookup"><span data-stu-id="8c678-111">The ENTSSO user interface</span></span>  
  
  <span data-ttu-id="8c678-112">在本部分中的主题介绍配置过程。</span><span class="sxs-lookup"><span data-stu-id="8c678-112">The topics in this section describe the configuration process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8c678-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="8c678-113">In This Section</span></span>  
  
-   [<span data-ttu-id="8c678-114">配置 XML 文件</span><span class="sxs-lookup"><span data-stu-id="8c678-114">Configuring the XML File</span></span>](../core/configuring-the-xml-file.md)  
  
-   [<span data-ttu-id="8c678-115">如何针对 ENTSSO MA 配置 MIIS</span><span class="sxs-lookup"><span data-stu-id="8c678-115">How to Configure MIIS for ENTSSO MA</span></span>](../core/how-to-configure-miis-for-entsso-ma.md)  
  
-   [<span data-ttu-id="8c678-116">如何配置 ENTSSO 以实现 MIIS 密码同步</span><span class="sxs-lookup"><span data-stu-id="8c678-116">How to Configure ENTSSO for MIIS Password Sync</span></span>](../core/how-to-configure-entsso-for-miis-password-sync.md)