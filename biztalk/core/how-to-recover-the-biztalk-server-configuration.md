---
title: "如何恢复 BizTalk Server 配置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c1d39e50-4296-49c7-bd1e-63b1325af168
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9935c2c565d78d0bc102d4aef86959c2a9066e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-recover-the-biztalk-server-configuration"></a><span data-ttu-id="24baa-102">如何恢复 BizTalk Server 配置</span><span class="sxs-lookup"><span data-stu-id="24baa-102">How to Recover the BizTalk Server Configuration</span></span>
<span data-ttu-id="24baa-103">作为恢复 BizTalk 服务器的一部分，你还必须导入安装 BizTalk Server 时所创建的配置文件。</span><span class="sxs-lookup"><span data-stu-id="24baa-103">As part of recovering your BizTalk server, you must also import the configuration file that you created when you installed BizTalk Server.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="24baa-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="24baa-104">Prerequisites</span></span>  
 <span data-ttu-id="24baa-105">必须以 Administrators 组成员的身份登录，才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="24baa-105">You must be logged on as a member of the Administrators group to perform this procedure.</span></span>  
  
### <a name="to-recover-the-biztalk-server-configuration"></a><span data-ttu-id="24baa-106">若要恢复的 BizTalk Server 配置</span><span class="sxs-lookup"><span data-stu-id="24baa-106">To recover the BizTalk Server configuration</span></span>  
  
1.  <span data-ttu-id="24baa-107">使用记事本编辑您以前备份的 BizTalk Server 配置文件，并输入的 BizTalk Server 服务的所有用户帐户密码。</span><span class="sxs-lookup"><span data-stu-id="24baa-107">Using Notepad, edit the BizTalk Server configuration file that you previously backed up, and enter the user account passwords for all of the BizTalk Server services.</span></span>  
  
2.  <span data-ttu-id="24baa-108">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 配置**。</span><span class="sxs-lookup"><span data-stu-id="24baa-108">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Configuration**.</span></span>  
  
3.  <span data-ttu-id="24baa-109">在**Microsoft BizTalk Server 配置**，单击**导入配置**。</span><span class="sxs-lookup"><span data-stu-id="24baa-109">In **Microsoft BizTalk Server Configuration**, click **Import Configuration**.</span></span>  
  
     <span data-ttu-id="24baa-110">验证有任何功能的前面显示任何失效图标。</span><span class="sxs-lookup"><span data-stu-id="24baa-110">Verify that there are no invalidation icons appearing in front of any feature.</span></span> <span data-ttu-id="24baa-111">如果有配置错误的任何功能，现在是时间来更正它们。</span><span class="sxs-lookup"><span data-stu-id="24baa-111">If any of the features have configuration errors, now is the time to correct them.</span></span>  
  
4.  <span data-ttu-id="24baa-112">单击“应用配置”。</span><span class="sxs-lookup"><span data-stu-id="24baa-112">Click **Apply Configuration**.</span></span>  
  
     <span data-ttu-id="24baa-113">在所有的 BizTalk Server 配置功能，请关闭配置窗口。</span><span class="sxs-lookup"><span data-stu-id="24baa-113">After all of the BizTalk Server features are configured, close the configuration window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24baa-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="24baa-114">See Also</span></span>  
 <span data-ttu-id="24baa-115">[恢复运行 BizTalk Server 的计算机](../core/recovering-a-computer-running-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="24baa-115">[Recovering a Computer Running BizTalk Server](../core/recovering-a-computer-running-biztalk-server.md) </span></span>  
 [<span data-ttu-id="24baa-116">如何备份的 BizTalk Server 配置</span><span class="sxs-lookup"><span data-stu-id="24baa-116">How to Back Up The BizTalk Server Configuration</span></span>](../core/how-to-back-up-the-biztalk-server-configuration.md)