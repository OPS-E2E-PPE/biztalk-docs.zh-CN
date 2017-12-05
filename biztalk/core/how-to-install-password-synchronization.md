---
title: "如何安装密码同步 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- installing, Password Synchronization [SSO]
- Password Synchronization [SSO], installing
ms.assetid: 8ace0401-b759-4ea3-91a0-be2aa8b5a5a4
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3a6a3f93e600a8e68581f09af8fcdbc77ed57af
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-install-password-synchronization"></a><span data-ttu-id="944a2-102">如何安装密码同步</span><span class="sxs-lookup"><span data-stu-id="944a2-102">How to Install Password Synchronization</span></span>
<span data-ttu-id="944a2-103">因为在默认的密码同步未安装单一登录与其他功能一起，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装，并且必须专门选择在安装过程。</span><span class="sxs-lookup"><span data-stu-id="944a2-103">As with the other Single Sign-On features, Password Synchronization is not installed in the default [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation, and must be specifically selected during setup.</span></span>  
  
### <a name="to-install-password-synchronization"></a><span data-ttu-id="944a2-104">安装密码同步</span><span class="sxs-lookup"><span data-stu-id="944a2-104">To install Password Synchronization</span></span>  
  
1.  <span data-ttu-id="944a2-105">在 BizTalk Server 光盘，浏览到 **\<CDRoot\>\Platforms\SSO**文件夹。</span><span class="sxs-lookup"><span data-stu-id="944a2-105">On the BizTalk Server CD, browse to the **\<CDRoot\>\Platforms\SSO** folder.</span></span>  
  
2.  <span data-ttu-id="944a2-106">运行**setup.exe**并按照向导中的说明。</span><span class="sxs-lookup"><span data-stu-id="944a2-106">Run **setup.exe** and follow the instructions in the wizard.</span></span>  
  
3.  <span data-ttu-id="944a2-107">选择**密码同步**功能并继续安装。</span><span class="sxs-lookup"><span data-stu-id="944a2-107">Select the **Password Synchronization** feature and proceed with the installation.</span></span>  
  
 <span data-ttu-id="944a2-108">除此之外，还需要使用密码同步适配器才能发送和接收对外部系统的密码更改。</span><span class="sxs-lookup"><span data-stu-id="944a2-108">In addition to this, Password synchronization adapters are necessary to send and receive password changes to the external system.</span></span> <span data-ttu-id="944a2-109">本部分中的主题将介绍如何配置您自己的适配器。</span><span class="sxs-lookup"><span data-stu-id="944a2-109">The topics in this section describe how to configure your own adapters.</span></span>  
  
 <span data-ttu-id="944a2-110">您也可以联系支持人员以获取有关可用的密码同步适配器的信息。</span><span class="sxs-lookup"><span data-stu-id="944a2-110">You can also contact support aliases to obtain information on available Password synchronization adapters.</span></span>  
  
 <span data-ttu-id="944a2-111">最后，若要捕获在 Active Directory 中所做的密码更改，则除了安装 ENTSSO 密码同步功能之外，还需在域控制器上安装组件才能捕获密码更改。</span><span class="sxs-lookup"><span data-stu-id="944a2-111">Finally, to capture password changes made in Active Directory, in addition to installing the ENTSSO Password Sync feature, components need to be installed on the domain controllers to capture password changes.</span></span>  
  
 <span data-ttu-id="944a2-112">必须在要从中捕获密码的所有域控制器上安装 Windows 密码捕获组件和密码更改通知服务 (PCNS)。</span><span class="sxs-lookup"><span data-stu-id="944a2-112">Both the Windows Password Capture component and Password Change Notification Service (PCNS) must be installed on all domain controllers from which you will be capturing passwords.</span></span> <span data-ttu-id="944a2-113">您可以从以下位置安装这些组件：</span><span class="sxs-lookup"><span data-stu-id="944a2-113">You can install these components from the following location:</span></span>  
  
 [<span data-ttu-id="944a2-114">http://go.microsoft.com/fwlink/?LinkId=68145</span><span class="sxs-lookup"><span data-stu-id="944a2-114">http://go.microsoft.com/fwlink/?LinkId=68145</span></span>](http://go.microsoft.com/fwlink/?LinkId=68145)  
  
 <span data-ttu-id="944a2-115">在域控制器上继续进行安装之前，请阅读附带的文档（也位于此文件夹中）。</span><span class="sxs-lookup"><span data-stu-id="944a2-115">Read the accompanying documentation (also located in this folder) before you proceed with the installation on the domain controller.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="944a2-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="944a2-116">See Also</span></span>  
 [<span data-ttu-id="944a2-117">密码同步</span><span class="sxs-lookup"><span data-stu-id="944a2-117">Password Synchronization</span></span>](../core/password-synchronization2.md)