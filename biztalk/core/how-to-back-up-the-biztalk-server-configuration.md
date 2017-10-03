---
title: "如何备份的 BizTalk Server 配置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14f89050-c204-4d44-a875-299e690489ef
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad54aba8f8f49adeb8534bdbe28add15f0fe9638
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-back-up-the-biztalk-server-configuration"></a><span data-ttu-id="6f601-102">如何备份 BizTalk Server 配置</span><span class="sxs-lookup"><span data-stu-id="6f601-102">How to Back Up The BizTalk Server Configuration</span></span>
<span data-ttu-id="6f601-103">作为备份 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的一部分，应当备份与运行 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的计算机相关联的配置设置。</span><span class="sxs-lookup"><span data-stu-id="6f601-103">As part of backing up [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you should back up the configuration settings associated with the computer running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="6f601-104">如果具有原始配置文件的副本，则在计算机发生硬件故障需要更换计算机时，将会极大地简化还原过程。</span><span class="sxs-lookup"><span data-stu-id="6f601-104">Having a copy of the original configuration file greatly simplifies the restoration process if you have a hardware failure that requires you to replace the computer.</span></span>  
  
 <span data-ttu-id="6f601-105">运行 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的每台计算机的配置设置都存储在由 BizTalk Server 配置管理器创建的 XML 文件中。</span><span class="sxs-lookup"><span data-stu-id="6f601-105">The configuration settings for each computer running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] are stored in an XML file created by the BizTalk Server Configuration Manager.</span></span> <span data-ttu-id="6f601-106">每当更改 BizTalk Server 的配置时，都应当将更新的配置文件导出到备份位置。</span><span class="sxs-lookup"><span data-stu-id="6f601-106">Any time you change the configuration of your BizTalk servers, you should export the updated configuration file to your backup location.</span></span> <span data-ttu-id="6f601-107">这有助于确保在必须替换 BizTalk Server 时配置文件可用。</span><span class="sxs-lookup"><span data-stu-id="6f601-107">This helps to ensure that the configuration file is available if you have to replace your BizTalk server.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6f601-108">先决条件</span><span class="sxs-lookup"><span data-stu-id="6f601-108">Prerequisites</span></span>  
 <span data-ttu-id="6f601-109">必须以 BizTalk Server Administrators 组成员的身份登录，才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="6f601-109">You must be logged on as a member of the BizTalk Server Administrators group to perform this procedure.</span></span>  
  
### <a name="to-back-up-the-biztalk-server-configuration"></a><span data-ttu-id="6f601-110">备份 BizTalk Server 配置</span><span class="sxs-lookup"><span data-stu-id="6f601-110">To back up the BizTalk Server configuration</span></span>  
  
1.  <span data-ttu-id="6f601-111">单击**启动**，单击**所有程序**，单击**Microsoft BizTalk Server**，然后单击**BizTalk Server 配置**。</span><span class="sxs-lookup"><span data-stu-id="6f601-111">Click **Start**, click **All Programs**, click **Microsoft BizTalk Server**, and then click **BizTalk Server Configuration**.</span></span>  
  
2.  <span data-ttu-id="6f601-112">在**Microsoft BizTalk Server 配置**，单击**导出配置**。</span><span class="sxs-lookup"><span data-stu-id="6f601-112">In **Microsoft BizTalk Server Configuration**, click **Export Configuration**.</span></span>  
  
3.  <span data-ttu-id="6f601-113">在**另存为**对话框中，浏览到你在其中存储你的备份的位置。</span><span class="sxs-lookup"><span data-stu-id="6f601-113">In the **Save As** dialog box, browse to the location where you store your backups.</span></span>  
  
4.  <span data-ttu-id="6f601-114">在**文件名**框中，为配置文件中，键入一个名称，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="6f601-114">In the **File name** box, type a name for the configuration file, and then click **Save**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f601-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6f601-115">See Also</span></span>  
 <span data-ttu-id="6f601-116">[备份运行 BizTalk Server 的计算机](../core/backing-up-a-computer-running-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="6f601-116">[Backing Up a Computer Running BizTalk Server](../core/backing-up-a-computer-running-biztalk-server.md) </span></span>  
 [<span data-ttu-id="6f601-117">如何恢复 BizTalk Server 配置</span><span class="sxs-lookup"><span data-stu-id="6f601-117">How to Recover the BizTalk Server Configuration</span></span>](../core/how-to-recover-the-biztalk-server-configuration.md)