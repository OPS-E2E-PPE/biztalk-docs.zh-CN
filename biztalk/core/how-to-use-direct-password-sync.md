---
title: 如何使用直接密码同步 |Microsoft Docs
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
ms.openlocfilehash: e9baa74b383ee30c1fba70c7f9bb966706d60142
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333537"
---
# <a name="how-to-use-direct-password-sync"></a><span data-ttu-id="4cb79-102">如何使用直接密码同步</span><span class="sxs-lookup"><span data-stu-id="4cb79-102">How to Use Direct Password Sync</span></span>
<span data-ttu-id="4cb79-103">此版本的企业单一登录包括了从 Windows 功能直接进行密码同步。</span><span class="sxs-lookup"><span data-stu-id="4cb79-103">This version of Enterprise Single Sign-On includes the Direct Password Sync from Windows feature.</span></span> <span data-ttu-id="4cb79-104">这使你可以绕过密码同步适配器和更新 SSO 数据库中直接从 Windows 中的密码。</span><span class="sxs-lookup"><span data-stu-id="4cb79-104">This enables you to bypass a Password Sync Adapter and update the password in the SSO Database directly from Windows.</span></span>  
  
 <span data-ttu-id="4cb79-105">从 Windows 直接进行密码同步是在以下情况下有用：</span><span class="sxs-lookup"><span data-stu-id="4cb79-105">Direct Password Sync from Windows is useful in the following situations:</span></span>  
  
-   <span data-ttu-id="4cb79-106">企业系统要求 Windows 到 Windows 的映射。</span><span class="sxs-lookup"><span data-stu-id="4cb79-106">Your enterprise system requires Windows to Windows mapping.</span></span>  
  
-   <span data-ttu-id="4cb79-107">您需要为 Windows 用户的密码更改时直接更新 SSO 数据库中的外部用户的密码。</span><span class="sxs-lookup"><span data-stu-id="4cb79-107">You need to update the External User’s password in the SSO database directly when a password change occurs for the Windows user.</span></span> <span data-ttu-id="4cb79-108">可以通过使用其他机制更改密码的后端系统上 （相对应的外部用户）。</span><span class="sxs-lookup"><span data-stu-id="4cb79-108">You can change the password on the back-end system (that corresponds to the external user) by using other mechanisms.</span></span> <span data-ttu-id="4cb79-109">例如，可以使用 Microsoft Identity Integration Server 更新中资源的访问控制工具 (RACF) 使用 RACF Management Agent IBM 大型机上的密码。</span><span class="sxs-lookup"><span data-stu-id="4cb79-109">For example, you can use Microsoft Identity Integration Server to update passwords in Resource Access Control Facility (RACF) on an IBM Mainframe using the RACF Management Agent.</span></span>  
  
### <a name="to-enable-direct-password-sync"></a><span data-ttu-id="4cb79-110">若要启用直接密码同步</span><span class="sxs-lookup"><span data-stu-id="4cb79-110">To enable Direct Password Sync</span></span>  
  
1.  <span data-ttu-id="4cb79-111">打开企业单一登录。</span><span class="sxs-lookup"><span data-stu-id="4cb79-111">Open Enterprise Single Sign-On.</span></span>  
  
2.  <span data-ttu-id="4cb79-112">在作用域窗格中，单击**关联应用程序**。</span><span class="sxs-lookup"><span data-stu-id="4cb79-112">In the scope pane, click **Affiliate Applications**.</span></span>  
  
3.  <span data-ttu-id="4cb79-113">右键单击相应**关联应用程序**。</span><span class="sxs-lookup"><span data-stu-id="4cb79-113">Right-click the appropriate **Affiliate Application**.</span></span>  
  
4.  <span data-ttu-id="4cb79-114">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="4cb79-114">Click **Properties**.</span></span>  
  
     <span data-ttu-id="4cb79-115">**关联的应用程序属性**对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="4cb79-115">The **Affiliate Applications Properties** dialog box appears.</span></span>  
  
5.  <span data-ttu-id="4cb79-116">单击**选项**选项卡。</span><span class="sxs-lookup"><span data-stu-id="4cb79-116">Click the **Options** tab.</span></span>  
  
6.  <span data-ttu-id="4cb79-117">选择**从 Windows 直接进行密码同步**复选框。</span><span class="sxs-lookup"><span data-stu-id="4cb79-117">Select the **Direct Password Sync from Windows** check box.</span></span>  
  
7.  <span data-ttu-id="4cb79-118">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="4cb79-118">Click **OK**.</span></span>