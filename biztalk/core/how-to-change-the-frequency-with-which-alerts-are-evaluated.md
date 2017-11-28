---
title: "如何更改的警报的频率进行评估 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 68f326ed-2017-4853-89b9-146cb0785554
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a686c7de8057fdf843ff855da109e77e8ba7b8ae
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-change-the-frequency-with-which-alerts-are-evaluated"></a><span data-ttu-id="5aa14-102">如何更改计算的警报的频率</span><span class="sxs-lookup"><span data-stu-id="5aa14-102">How to Change the Frequency With Which Alerts Are Evaluated</span></span>
<span data-ttu-id="5aa14-103">有时会出现这样的情况：使用默认设置部署 SQL Notifications Services 生成器后，它可能无法及时处理 BAM 事件提供程序引发的事件。</span><span class="sxs-lookup"><span data-stu-id="5aa14-103">There are cases in which the SQL Notifications services generator may not keep up with events being raised by the BAM event provider when deployed with the default settings.</span></span> <span data-ttu-id="5aa14-104">您可以通过修改 Notification Services adf.xml 文件来加快评估事件是否需要发出警报的频率（量程持续时间）。</span><span class="sxs-lookup"><span data-stu-id="5aa14-104">You can increase the frequency (the quantum duration) with which events are evaluated for alerts by modifying the Notification Services adf.xml file.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5aa14-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="5aa14-105">Prerequisites</span></span>  
 <span data-ttu-id="5aa14-106">若要执行此过程，必须以具有主导入数据库读写权限的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 组成员的身份（通常是 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators 组）登录。</span><span class="sxs-lookup"><span data-stu-id="5aa14-106">To perform this procedure you must be logged on as a member of a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] group that has permissions to read and write the Primary Import database, typically this will be a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-modify-the-notification-services-generator-quantum-duration"></a><span data-ttu-id="5aa14-107">修改 Notification Services 生成器量程持续时间</span><span class="sxs-lookup"><span data-stu-id="5aa14-107">To modify the Notification Services generator quantum duration</span></span>  
  
1.  <span data-ttu-id="5aa14-108">打开 Notification Services 命令提示窗口。</span><span class="sxs-lookup"><span data-stu-id="5aa14-108">Open the Notification Services Command prompt.</span></span> <span data-ttu-id="5aa14-109">单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2005**，单击**配置工具**，然后单击**通知服务命令提示符**。</span><span class="sxs-lookup"><span data-stu-id="5aa14-109">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2005**, click **Configuration Tools**, and then click **Notification Services Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="5aa14-110">获取 Notification Services 配置文件。</span><span class="sxs-lookup"><span data-stu-id="5aa14-110">Get the Notification Services configuration file.</span></span> <span data-ttu-id="5aa14-111">在命令提示符处，键入： **cscript ProcessBamNSFiles.vbs-Get config.xml adf.xml \<PimaryImport 数据库服务器 > \< PimaryImport 数据库名称 >**。</span><span class="sxs-lookup"><span data-stu-id="5aa14-111">At the command prompt, type: **cscript ProcessBamNSFiles.vbs -Get config.xml adf.xml \<PimaryImport database server> \< PimaryImport database name>**.</span></span>  
  
3.  <span data-ttu-id="5aa14-112">修改或添加\<QuantumDuration > 元素下的\<ApplicationExecutionSettings > 中的节点 adf.xml 文件中。</span><span class="sxs-lookup"><span data-stu-id="5aa14-112">Modify or add the \<QuantumDuration> element under the \<ApplicationExecutionSettings> node in the in the adf.xml file.</span></span> <span data-ttu-id="5aa14-113">QuantumDuration 元素的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=78803](http://go.microsoft.com/fwlink/?LinkId=78803)。</span><span class="sxs-lookup"><span data-stu-id="5aa14-113">For more information on the QuantumDuration element, see [http://go.microsoft.com/fwlink/?LinkId=78803](http://go.microsoft.com/fwlink/?LinkId=78803).</span></span>  
  
4.  <span data-ttu-id="5aa14-114">在命令提示符处，键入： **cscript ProcessBamNSFiles.vbs-更新 config.xml adf.xml \<PimaryImport 数据库服务器 > \< PimaryImport 数据库名称 >。**</span><span class="sxs-lookup"><span data-stu-id="5aa14-114">At the command prompt, type: **cscript ProcessBamNSFiles.vbs -Update  config.xml adf.xml  \<PimaryImport database server> \< PimaryImport database name>.**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5aa14-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5aa14-115">See Also</span></span>  
 [<span data-ttu-id="5aa14-116">BAM 通知的命令行脚本服务配置文件</span><span class="sxs-lookup"><span data-stu-id="5aa14-116">BAM Command-Line Script for Notification Services Configuration Files</span></span>](../core/bam-command-line-script-for-notification-services-configuration-files.md)