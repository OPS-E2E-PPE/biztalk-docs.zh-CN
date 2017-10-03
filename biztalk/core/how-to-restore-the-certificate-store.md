---
title: "如何还原证书存储区 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0c6f7551-d119-4668-9b52-6013f69a0302
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aaeee6b762cf5af15ca7cba34864abd86682d4df
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-restore-the-certificate-store"></a><span data-ttu-id="e5b18-102">如何还原证书存储</span><span class="sxs-lookup"><span data-stu-id="e5b18-102">How to Restore the Certificate Store</span></span>
<span data-ttu-id="e5b18-103">在恢复 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的过程中，必须还原证书存储。</span><span class="sxs-lookup"><span data-stu-id="e5b18-103">As a part of recovering [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you must restore the certificate store.</span></span> <span data-ttu-id="e5b18-104">如果要恢复 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 标准版，则必须使用此过程来还原证书存储。</span><span class="sxs-lookup"><span data-stu-id="e5b18-104">If you are recovering [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Standard Edition, you must use this procedure to restore the certificate store.</span></span> <span data-ttu-id="e5b18-105">在恢复 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的所有其他版本时，不需要执行此过程，因为恢复过程将自动为您还原证书存储。</span><span class="sxs-lookup"><span data-stu-id="e5b18-105">You do not need to perform this procedure when recovering all other editions of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] because the recovery process automatically restores the certificate store for you.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e5b18-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="e5b18-106">Prerequisites</span></span>  
 <span data-ttu-id="e5b18-107">必须以 Administrators 组成员的身份登录，才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="e5b18-107">You must be logged on as a member of the Administrators group to perform this procedure.</span></span>  
  
### <a name="to-restore-the-certificate-store-biztalk-server-standard-edition"></a><span data-ttu-id="e5b18-108">还原证书存储（BizTalk Server 标准版）</span><span class="sxs-lookup"><span data-stu-id="e5b18-108">To restore the certificate store (BizTalk Server Standard Edition)</span></span>  
  
1.  <span data-ttu-id="e5b18-109">单击**启动**，单击**所有程序**，然后单击**Internet Explorer**。</span><span class="sxs-lookup"><span data-stu-id="e5b18-109">Click **Start**, click **All Programs**, and then click **Internet Explorer**.</span></span>  
  
2.  <span data-ttu-id="e5b18-110">上**工具**菜单上，单击**Internet 选项**。</span><span class="sxs-lookup"><span data-stu-id="e5b18-110">On the **Tools** menu, click **Internet Options**.</span></span>  
  
3.  <span data-ttu-id="e5b18-111">在**Internet 选项**对话框中，单击**内容**选项卡上，并依次**证书**。</span><span class="sxs-lookup"><span data-stu-id="e5b18-111">In the **Internet Options** dialog box, click the **Content** tab, and then click **Certificates**.</span></span>  
  
4.  <span data-ttu-id="e5b18-112">在**证书**对话框中，单击**其他人**选项卡上，并依次**导入**。</span><span class="sxs-lookup"><span data-stu-id="e5b18-112">In the **Certificates** dialog box, click the **Other People** tab, and then click **Import**.</span></span>  
  
5.  <span data-ttu-id="e5b18-113">在**证书导入向导**，单击**取消**。</span><span class="sxs-lookup"><span data-stu-id="e5b18-113">In the **Certificate Import Wizard**, click **Cancel**.</span></span>  
  
     <span data-ttu-id="e5b18-114">这将创建**通讯簿**注册表中的 hive。</span><span class="sxs-lookup"><span data-stu-id="e5b18-114">This creates the **AddressBook** hive in the registry.</span></span>  
  
6.  <span data-ttu-id="e5b18-115">在**证书**对话框中，单击**关闭**。</span><span class="sxs-lookup"><span data-stu-id="e5b18-115">In the **Certificates** dialog box, click **Close**.</span></span>  
  
7.  <span data-ttu-id="e5b18-116">在**Internet 选项**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="e5b18-116">In the **Internet Options** dialog box, click **OK**.</span></span>  
  
8.  <span data-ttu-id="e5b18-117">单击**文件**，然后单击**关闭**退出 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="e5b18-117">Click **File**, and then click **Close** to exit Internet Explorer.</span></span>  
  
9. <span data-ttu-id="e5b18-118">单击**启动**，单击**运行**，类型**regedit**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="e5b18-118">Click **Start**, click **Run**, type **regedit**, and then click **OK**.</span></span>  
  
10. <span data-ttu-id="e5b18-119">在注册表编辑器中，导航到以下注册表项：</span><span class="sxs-lookup"><span data-stu-id="e5b18-119">In Registry Editor, navigate to the following registry key:</span></span>  
  
     <span data-ttu-id="e5b18-120">**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\SystemCertificates**</span><span class="sxs-lookup"><span data-stu-id="e5b18-120">**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\SystemCertificates**</span></span>  
  
11. <span data-ttu-id="e5b18-121">验证**通讯簿**配置单元已存在。</span><span class="sxs-lookup"><span data-stu-id="e5b18-121">Verify that the **AddressBook** hive is present.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5b18-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e5b18-122">See Also</span></span>  
 [<span data-ttu-id="e5b18-123">恢复运行 BizTalk Server 的计算机</span><span class="sxs-lookup"><span data-stu-id="e5b18-123">Recovering a Computer Running BizTalk Server</span></span>](../core/recovering-a-computer-running-biztalk-server.md)