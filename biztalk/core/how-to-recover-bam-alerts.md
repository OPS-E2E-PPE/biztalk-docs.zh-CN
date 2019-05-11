---
title: 如何恢复 BAM 警报 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 56c477b4-4605-4763-b20a-3baf4529f13f
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5fc3e51593b0a01fb43111f58f01ec07efdc09f4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335622"
---
# <a name="how-to-recover-bam-alerts"></a><span data-ttu-id="51b2e-102">如何恢复 BAM 警报</span><span class="sxs-lookup"><span data-stu-id="51b2e-102">How to Recover BAM Alerts</span></span>
<span data-ttu-id="51b2e-103">作为恢复的一部分[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，如果使用业务活动监视 (BAM)，则还必须恢复 BAM 警报。</span><span class="sxs-lookup"><span data-stu-id="51b2e-103">As a part of recovering [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], if you are using Business Activity Monitoring (BAM), you must also recover the BAM alerts.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="51b2e-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="51b2e-104">Prerequisites</span></span>  
 <span data-ttu-id="51b2e-105">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="51b2e-105">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group to perform this procedure.</span></span>  
  
### <a name="to-recover-bam-alerts-sql-server-2008"></a><span data-ttu-id="51b2e-106">若要恢复 BAM 警报 (SQL Server 2008)</span><span class="sxs-lookup"><span data-stu-id="51b2e-106">To recover BAM alerts (SQL Server 2008)</span></span>  
  
1.  <span data-ttu-id="51b2e-107">单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008**，单击**配置工具**，然后单击**Notification Services 命令提示符下**。</span><span class="sxs-lookup"><span data-stu-id="51b2e-107">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008**, click **Configuration Tools**, and then click **Notification Services Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="51b2e-108">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="51b2e-108">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="51b2e-109">**nscontrol register-name BamAlerts-server***\<ServerName\>***-服务-serviceusername"** *\<ServiceUserName\>* **"-servicepassword"** *\<ServicePassword\>* **"** </span><span class="sxs-lookup"><span data-stu-id="51b2e-109">**nscontrol register -name BamAlerts -server**  *\<ServerName\>*  **-service -serviceusername "** *\<ServiceUserName\>* **" -servicepassword "** *\<ServicePassword\>* **"**</span></span>  
  
     <span data-ttu-id="51b2e-110">这可使 Notification Services 登录到正确的数据库 （此信息保留在服务计算机的注册表中由 nscontrol）。</span><span class="sxs-lookup"><span data-stu-id="51b2e-110">This enables Notification Services to log on to the correct database (this information is maintained in the registry of the service computer by nscontrol).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="51b2e-111">请记得使用新的 Notification Services 数据库服务器 **-服务器**选项时重新注册该服务。</span><span class="sxs-lookup"><span data-stu-id="51b2e-111">Remember to use the new Notification Services databases server in the **-server** option when re-registering the service.</span></span> <span data-ttu-id="51b2e-112">此外，您应使用新的 Notification Services 服务的同一用户名称与旧。</span><span class="sxs-lookup"><span data-stu-id="51b2e-112">In addition, you should use the same user name for the new Notification Services service as the old one.</span></span>  
  
3.  <span data-ttu-id="51b2e-113">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="51b2e-113">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="51b2e-114">在命令提示符处，键入： **net start NS$ BamAlerts**。</span><span class="sxs-lookup"><span data-stu-id="51b2e-114">At the command prompt, type: **net start NS$BamAlerts**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51b2e-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="51b2e-115">See Also</span></span>  
 [<span data-ttu-id="51b2e-116">恢复运行 BizTalk Server 的计算机</span><span class="sxs-lookup"><span data-stu-id="51b2e-116">Recovering a Computer Running BizTalk Server</span></span>](../core/recovering-a-computer-running-biztalk-server.md)