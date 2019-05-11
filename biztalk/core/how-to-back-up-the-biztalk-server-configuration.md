---
title: 如何备份 BizTalk Server 配置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14f89050-c204-4d44-a875-299e690489ef
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9da0d382752a7f3469a8f10a3f2550b06fe84bcb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342658"
---
# <a name="how-to-back-up-the-biztalk-server-configuration"></a><span data-ttu-id="b6105-102">如何备份 BizTalk Server 配置</span><span class="sxs-lookup"><span data-stu-id="b6105-102">How to Back Up The BizTalk Server Configuration</span></span>
<span data-ttu-id="b6105-103">作为备份的一部分[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，应该备份与运行的计算机关联的配置设置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b6105-103">As part of backing up [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you should back up the configuration settings associated with the computer running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="b6105-104">拥有一份原始配置文件，极大地简化还原过程，如果有需要替换的计算机的硬件故障。</span><span class="sxs-lookup"><span data-stu-id="b6105-104">Having a copy of the original configuration file greatly simplifies the restoration process if you have a hardware failure that requires you to replace the computer.</span></span>  
  
 <span data-ttu-id="b6105-105">运行每个计算机的配置设置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]存储在 BizTalk Server 配置管理器创建的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="b6105-105">The configuration settings for each computer running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] are stored in an XML file created by the BizTalk Server Configuration Manager.</span></span> <span data-ttu-id="b6105-106">每当您更改的 BizTalk 服务器，配置应导出到备份位置更新的配置文件。</span><span class="sxs-lookup"><span data-stu-id="b6105-106">Any time you change the configuration of your BizTalk servers, you should export the updated configuration file to your backup location.</span></span> <span data-ttu-id="b6105-107">这有助于确保在配置文件可用，如果必须替换 BizTalk server。</span><span class="sxs-lookup"><span data-stu-id="b6105-107">This helps to ensure that the configuration file is available if you have to replace your BizTalk server.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b6105-108">先决条件</span><span class="sxs-lookup"><span data-stu-id="b6105-108">Prerequisites</span></span>  
 <span data-ttu-id="b6105-109">您必须为要执行此过程的 BizTalk Server Administrators 组的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="b6105-109">You must be logged on as a member of the BizTalk Server Administrators group to perform this procedure.</span></span>  
  
### <a name="to-back-up-the-biztalk-server-configuration"></a><span data-ttu-id="b6105-110">若要备份 BizTalk Server 配置</span><span class="sxs-lookup"><span data-stu-id="b6105-110">To back up the BizTalk Server configuration</span></span>  
  
1.  <span data-ttu-id="b6105-111">单击**启动**，单击**所有程序**，单击**Microsoft BizTalk Server**，然后单击**BizTalk Server 配置**。</span><span class="sxs-lookup"><span data-stu-id="b6105-111">Click **Start**, click **All Programs**, click **Microsoft BizTalk Server**, and then click **BizTalk Server Configuration**.</span></span>  
  
2.  <span data-ttu-id="b6105-112">在中**Microsoft BizTalk Server 配置**，单击**导出配置**。</span><span class="sxs-lookup"><span data-stu-id="b6105-112">In **Microsoft BizTalk Server Configuration**, click **Export Configuration**.</span></span>  
  
3.  <span data-ttu-id="b6105-113">在中**另存为**对话框中，浏览到存储备份的位置。</span><span class="sxs-lookup"><span data-stu-id="b6105-113">In the **Save As** dialog box, browse to the location where you store your backups.</span></span>  
  
4.  <span data-ttu-id="b6105-114">在中**文件名**框中，键入配置文件的名称，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="b6105-114">In the **File name** box, type a name for the configuration file, and then click **Save**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6105-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="b6105-115">See Also</span></span>  
 <span data-ttu-id="b6105-116">[备份运行 BizTalk Server 的计算机](../core/backing-up-a-computer-running-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="b6105-116">[Backing Up a Computer Running BizTalk Server](../core/backing-up-a-computer-running-biztalk-server.md) </span></span>  
 [<span data-ttu-id="b6105-117">如何恢复 BizTalk Server 配置</span><span class="sxs-lookup"><span data-stu-id="b6105-117">How to Recover the BizTalk Server Configuration</span></span>](../core/how-to-recover-the-biztalk-server-configuration.md)