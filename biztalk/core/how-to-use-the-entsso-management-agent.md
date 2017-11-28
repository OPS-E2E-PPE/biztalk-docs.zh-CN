---
title: "如何使用 ENTSSO 管理代理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9c89b494-db12-4d2a-a030-6acd34489cab
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03c0f7d2c04a2707cf965f64ff7a559d8642a12c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-the-entsso-management-agent"></a><span data-ttu-id="73efa-102">如何使用 ENTSSO 管理代理</span><span class="sxs-lookup"><span data-stu-id="73efa-102">How to Use the ENTSSO Management Agent</span></span>
<span data-ttu-id="73efa-103">企业单一登录 (SSO) 的此版本包含 Microsoft Identity Integration Server (MIIS) 的管理代理 (MA)，后者将企业 SSO 与 MIIS 的帐户同步功能集成在一起。</span><span class="sxs-lookup"><span data-stu-id="73efa-103">This version of Enterprise Single Sign-On (SSO) contains a Management Agent (MA) for Microsoft Identity Integration Server (MIIS), which integrates Enterprise SSO with the account synchronization capabilities of MIIS.</span></span> <span data-ttu-id="73efa-104">这样，MIIS 管理员便可管理 SSO 数据库中的 SSO 映射。</span><span class="sxs-lookup"><span data-stu-id="73efa-104">This enables an MIIS administrator to manage SSO mappings in the SSO Database.</span></span>  
  
 <span data-ttu-id="73efa-105">在企业 SSO 映射创建 Windows 域帐户之间 (*域名 \ 用户名*) 和外部凭据。</span><span class="sxs-lookup"><span data-stu-id="73efa-105">In Enterprise SSO, mappings are created between Windows Domain accounts (*domainname\username*) and external credentials.</span></span> <span data-ttu-id="73efa-106">如果你有 Active Directory 管理代理，并管理代理为外部数据源 (示例： RACF MA)，你可以使用企业 SSO MA (ENTSSO MA) 来管理 SSO 数据库中的映射。</span><span class="sxs-lookup"><span data-stu-id="73efa-106">If you have an Active Directory Management Agent, and the Management Agent for the external Data Source (example: RACF MA), you can use the Enterprise SSO MA (ENTSSO MA) to manage mappings in the SSO Database.</span></span> <span data-ttu-id="73efa-107">ENTSSO MA 是*基于调用的导出*仅管理代理。</span><span class="sxs-lookup"><span data-stu-id="73efa-107">ENTSSO MA is a *Call-Based Export* Management Agent only.</span></span>  
  
 <span data-ttu-id="73efa-108">您需在三个不同的部分配置该管理代理：</span><span class="sxs-lookup"><span data-stu-id="73efa-108">You configure the Management Agent in three separate parts:</span></span>  
  
-   <span data-ttu-id="73efa-109">配置文件 (ENTSSO.xml)</span><span class="sxs-lookup"><span data-stu-id="73efa-109">A configuration file (ENTSSO.xml)</span></span>  
  
-   <span data-ttu-id="73efa-110">MIIS 用户界面</span><span class="sxs-lookup"><span data-stu-id="73efa-110">The MIIS user interface</span></span>  
  
-   <span data-ttu-id="73efa-111">ENTSSO 用户界面</span><span class="sxs-lookup"><span data-stu-id="73efa-111">The ENTSSO user interface</span></span>  
  
 <span data-ttu-id="73efa-112">本部分中的主题将介绍这一配置过程。</span><span class="sxs-lookup"><span data-stu-id="73efa-112">The topics in this section describe the configuration process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="73efa-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="73efa-113">In This Section</span></span>  
  
-   [<span data-ttu-id="73efa-114">配置 XML 文件</span><span class="sxs-lookup"><span data-stu-id="73efa-114">Configuring the XML File</span></span>](../core/configuring-the-xml-file.md)  
  
-   [<span data-ttu-id="73efa-115">如何为 ENTSSO MA 配置 MIIS</span><span class="sxs-lookup"><span data-stu-id="73efa-115">How to Configure MIIS for ENTSSO MA</span></span>](../core/how-to-configure-miis-for-entsso-ma.md)  
  
-   [<span data-ttu-id="73efa-116">如何配置 ENTSSO miis 进行密码同步</span><span class="sxs-lookup"><span data-stu-id="73efa-116">How to Configure ENTSSO for MIIS Password Sync</span></span>](../core/how-to-configure-entsso-for-miis-password-sync.md)