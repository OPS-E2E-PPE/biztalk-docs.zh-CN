---
title: 如何使用直接密码同步 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d1334c2f-2020-46ea-a98c-f7688813e38c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6080589271d845432e875cb335a2ef354c9784ca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255941"
---
# <a name="how-to-use-direct-password-sync"></a><span data-ttu-id="d92ec-102">如何使用直接密码同步</span><span class="sxs-lookup"><span data-stu-id="d92ec-102">How to Use Direct Password Sync</span></span>
<span data-ttu-id="d92ec-103">此版本的企业单一登录包括了从 Windows 直接进行密码同步的功能。</span><span class="sxs-lookup"><span data-stu-id="d92ec-103">This version of Enterprise Single Sign-On includes the Direct Password Sync from Windows feature.</span></span> <span data-ttu-id="d92ec-104">这样，您便可以绕过密码同步适配器，直接从 Windows 更新 SSO 数据库中的密码。</span><span class="sxs-lookup"><span data-stu-id="d92ec-104">This enables you to bypass a Password Sync Adapter and update the password in the SSO Database directly from Windows.</span></span>  
  
 <span data-ttu-id="d92ec-105">从 Windows 直接进行密码同步这一功能在以下情况下十分有用：</span><span class="sxs-lookup"><span data-stu-id="d92ec-105">Direct Password Sync from Windows is useful in the following situations:</span></span>  
  
-   <span data-ttu-id="d92ec-106">您的企业系统要求 Windows 到 Windows 的映射。</span><span class="sxs-lookup"><span data-stu-id="d92ec-106">Your enterprise system requires Windows to Windows mapping.</span></span>  
  
-   <span data-ttu-id="d92ec-107">在 Windows 用户的密码发生更改时，您需要对 SSO 数据库中的外部用户的密码进行更新。</span><span class="sxs-lookup"><span data-stu-id="d92ec-107">You need to update the External User’s password in the SSO database directly when a password change occurs for the Windows user.</span></span> <span data-ttu-id="d92ec-108">可以使用其他机制更改外部用户所对应的后端系统中的密码。</span><span class="sxs-lookup"><span data-stu-id="d92ec-108">You can change the password on the back-end system (that corresponds to the external user) by using other mechanisms.</span></span> <span data-ttu-id="d92ec-109">例如，可以使用 Microsoft Identity Integration Server，通过 RACF Management Agent 更新 IBM 大型机上 Resource Access Control Facility (RACF) 中的密码。</span><span class="sxs-lookup"><span data-stu-id="d92ec-109">For example, you can use Microsoft Identity Integration Server to update passwords in Resource Access Control Facility (RACF) on an IBM Mainframe using the RACF Management Agent.</span></span>  
  
### <a name="to-enable-direct-password-sync"></a><span data-ttu-id="d92ec-110">启用直接密码同步</span><span class="sxs-lookup"><span data-stu-id="d92ec-110">To enable Direct Password Sync</span></span>  
  
1.  <span data-ttu-id="d92ec-111">打开企业单一登录。</span><span class="sxs-lookup"><span data-stu-id="d92ec-111">Open Enterprise Single Sign-On.</span></span>  
  
2.  <span data-ttu-id="d92ec-112">在作用域窗格中，单击**Affiliate 应用程序**。</span><span class="sxs-lookup"><span data-stu-id="d92ec-112">In the scope pane, click **Affiliate Applications**.</span></span>  
  
3.  <span data-ttu-id="d92ec-113">右键单击相应**Affiliate 应用程序**。</span><span class="sxs-lookup"><span data-stu-id="d92ec-113">Right-click the appropriate **Affiliate Application**.</span></span>  
  
4.  <span data-ttu-id="d92ec-114">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="d92ec-114">Click **Properties**.</span></span>  
  
     <span data-ttu-id="d92ec-115">**Affiliate 应用程序属性**对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="d92ec-115">The **Affiliate Applications Properties** dialog box appears.</span></span>  
  
5.  <span data-ttu-id="d92ec-116">单击**选项**选项卡。</span><span class="sxs-lookup"><span data-stu-id="d92ec-116">Click the **Options** tab.</span></span>  
  
6.  <span data-ttu-id="d92ec-117">选择**直接从 Windows 的密码同步**复选框。</span><span class="sxs-lookup"><span data-stu-id="d92ec-117">Select the **Direct Password Sync from Windows** check box.</span></span>  
  
7.  <span data-ttu-id="d92ec-118">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="d92ec-118">Click **OK**.</span></span>