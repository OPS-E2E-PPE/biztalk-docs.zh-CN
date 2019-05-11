---
title: 如何更改的警报的频率进行评估 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 68f326ed-2017-4853-89b9-146cb0785554
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de8ef990f851b9268e4cd6496b57a38318034534
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342441"
---
# <a name="how-to-change-the-frequency-with-which-alerts-are-evaluated"></a><span data-ttu-id="3c449-102">如何更改的警报的频率进行评估</span><span class="sxs-lookup"><span data-stu-id="3c449-102">How to Change the Frequency With Which Alerts Are Evaluated</span></span>
<span data-ttu-id="3c449-103">有些情况下在其中 SQL Notifications services 生成器可能无法及时处理 BAM 事件提供程序使用默认设置部署时所引发的事件。</span><span class="sxs-lookup"><span data-stu-id="3c449-103">There are cases in which the SQL Notifications services generator may not keep up with events being raised by the BAM event provider when deployed with the default settings.</span></span> <span data-ttu-id="3c449-104">您可以增加与评估事件警报通过修改 Notification Services adf.xml 文件的频率 （量程持续时间）。</span><span class="sxs-lookup"><span data-stu-id="3c449-104">You can increase the frequency (the quantum duration) with which events are evaluated for alerts by modifying the Notification Services adf.xml file.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3c449-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="3c449-105">Prerequisites</span></span>  
 <span data-ttu-id="3c449-106">若要执行此过程必须作为的成员身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]属于有权读取和写入主导入数据库中，通常是组[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。</span><span class="sxs-lookup"><span data-stu-id="3c449-106">To perform this procedure you must be logged on as a member of a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] group that has permissions to read and write the Primary Import database, typically this will be a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-modify-the-notification-services-generator-quantum-duration"></a><span data-ttu-id="3c449-107">若要修改 Notification Services 生成器量程持续时间</span><span class="sxs-lookup"><span data-stu-id="3c449-107">To modify the Notification Services generator quantum duration</span></span>  
  
1.  <span data-ttu-id="3c449-108">打开 Notification Services 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="3c449-108">Open the Notification Services Command prompt.</span></span> <span data-ttu-id="3c449-109">单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2005**，单击**配置工具**，然后单击**Notification Services 命令提示符下**。</span><span class="sxs-lookup"><span data-stu-id="3c449-109">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2005**, click **Configuration Tools**, and then click **Notification Services Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="3c449-110">获取 Notification Services 配置文件。</span><span class="sxs-lookup"><span data-stu-id="3c449-110">Get the Notification Services configuration file.</span></span> <span data-ttu-id="3c449-111">在命令提示符处，键入： **cscript ProcessBamNSFiles.vbs-Get config.xml adf.xml \<PimaryImport 数据库服务器\> \< PimaryImport 数据库名称\>**。</span><span class="sxs-lookup"><span data-stu-id="3c449-111">At the command prompt, type: **cscript ProcessBamNSFiles.vbs -Get config.xml adf.xml \<PimaryImport database server\> \< PimaryImport database name\>**.</span></span>  
  
3.  <span data-ttu-id="3c449-112">修改或添加\<QuantumDuration\>元素下的\<ApplicationExecutionSettings\>中的节点在 adf.xml 文件中。</span><span class="sxs-lookup"><span data-stu-id="3c449-112">Modify or add the \<QuantumDuration\> element under the \<ApplicationExecutionSettings\> node in the in the adf.xml file.</span></span> <span data-ttu-id="3c449-113">有关 QuantumDuration 元素的详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=78803 ](http://go.microsoft.com/fwlink/?LinkId=78803)。</span><span class="sxs-lookup"><span data-stu-id="3c449-113">For more information on the QuantumDuration element, see [http://go.microsoft.com/fwlink/?LinkId=78803](http://go.microsoft.com/fwlink/?LinkId=78803).</span></span>  
  
4.  <span data-ttu-id="3c449-114">在命令提示符处，键入： **cscript ProcessBamNSFiles.vbs-更新 config.xml adf.xml \<PimaryImport 数据库服务器\> \< PimaryImport 数据库名称\>。**</span><span class="sxs-lookup"><span data-stu-id="3c449-114">At the command prompt, type: **cscript ProcessBamNSFiles.vbs -Update  config.xml adf.xml  \<PimaryImport database server\> \< PimaryImport database name\>.**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c449-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="3c449-115">See Also</span></span>  
 [<span data-ttu-id="3c449-116">用于 Notification Services 配置文件的 BAM 命令行脚本</span><span class="sxs-lookup"><span data-stu-id="3c449-116">BAM Command-Line Script for Notification Services Configuration Files</span></span>](../core/bam-command-line-script-for-notification-services-configuration-files.md)