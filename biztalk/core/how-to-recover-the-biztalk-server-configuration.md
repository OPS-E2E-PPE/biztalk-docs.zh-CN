---
title: 如何恢复 BizTalk Server 配置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c1d39e50-4296-49c7-bd1e-63b1325af168
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 179ff0690c7c07dcf58bf2d7fd92a885435509cc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980334"
---
# <a name="how-to-recover-the-biztalk-server-configuration"></a><span data-ttu-id="d4616-102">如何恢复 BizTalk Server 配置</span><span class="sxs-lookup"><span data-stu-id="d4616-102">How to Recover the BizTalk Server Configuration</span></span>
<span data-ttu-id="d4616-103">作为恢复 BizTalk server 的一部分，您还必须导入安装 BizTalk Server 时所创建的配置文件。</span><span class="sxs-lookup"><span data-stu-id="d4616-103">As part of recovering your BizTalk server, you must also import the configuration file that you created when you installed BizTalk Server.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d4616-104">必要條件</span><span class="sxs-lookup"><span data-stu-id="d4616-104">Prerequisites</span></span>  
 <span data-ttu-id="d4616-105">必须以 Administrators 组成员的身份登录，才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="d4616-105">You must be logged on as a member of the Administrators group to perform this procedure.</span></span>  
  
### <a name="to-recover-the-biztalk-server-configuration"></a><span data-ttu-id="d4616-106">若要恢复 BizTalk Server 配置</span><span class="sxs-lookup"><span data-stu-id="d4616-106">To recover the BizTalk Server configuration</span></span>  
  
1. <span data-ttu-id="d4616-107">使用记事本，编辑您以前备份的 BizTalk Server 配置文件，并输入用户帐户密码的所有 BizTalk Server 服务。</span><span class="sxs-lookup"><span data-stu-id="d4616-107">Using Notepad, edit the BizTalk Server configuration file that you previously backed up, and enter the user account passwords for all of the BizTalk Server services.</span></span>  
  
2. <span data-ttu-id="d4616-108">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 配置**。</span><span class="sxs-lookup"><span data-stu-id="d4616-108">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Configuration**.</span></span>  
  
3. <span data-ttu-id="d4616-109">在中**Microsoft BizTalk Server 配置**，单击**导入配置**。</span><span class="sxs-lookup"><span data-stu-id="d4616-109">In **Microsoft BizTalk Server Configuration**, click **Import Configuration**.</span></span>  
  
    <span data-ttu-id="d4616-110">验证出现任何功能的前面没有失效图标。</span><span class="sxs-lookup"><span data-stu-id="d4616-110">Verify that there are no invalidation icons appearing in front of any feature.</span></span> <span data-ttu-id="d4616-111">如果有配置错误的任何功能，现在是时候更正它们。</span><span class="sxs-lookup"><span data-stu-id="d4616-111">If any of the features have configuration errors, now is the time to correct them.</span></span>  
  
4. <span data-ttu-id="d4616-112">单击“应用配置”。</span><span class="sxs-lookup"><span data-stu-id="d4616-112">Click **Apply Configuration**.</span></span>  
  
    <span data-ttu-id="d4616-113">别忘了 BizTalk Server 的已配置的功能，请关闭配置窗口。</span><span class="sxs-lookup"><span data-stu-id="d4616-113">After all of the BizTalk Server features are configured, close the configuration window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4616-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="d4616-114">See Also</span></span>  
 <span data-ttu-id="d4616-115">[恢复运行 BizTalk Server 的计算机](../core/recovering-a-computer-running-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="d4616-115">[Recovering a Computer Running BizTalk Server](../core/recovering-a-computer-running-biztalk-server.md) </span></span>  
 [<span data-ttu-id="d4616-116">如何备份 BizTalk Server 配置</span><span class="sxs-lookup"><span data-stu-id="d4616-116">How to Back Up The BizTalk Server Configuration</span></span>](../core/how-to-back-up-the-biztalk-server-configuration.md)