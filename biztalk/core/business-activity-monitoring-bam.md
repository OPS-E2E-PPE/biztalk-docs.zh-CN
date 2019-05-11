---
title: 业务活动监视 (BAM) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM, tools
- utilities, Tracking Profile Deployment Utility
- BAM, deployment process
- BAM
- BAM, presentation layers
- BAM, Tracking Profile Deployment utility
- BAM, about BAM
- BAM, data storage
- BAM Management utility
- Tracking Profile Deployment utility
- BAM, runtime process
- BAM, design time
- BAM, data insertion
- BAM, data consumption
- BAM, BAM Management utility
- BAM, processing
ms.assetid: a8ad48b1-6891-4bbb-b125-27d224e49293
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: acac201eac5ec76c0d6f9d06a97c58aaa3b4af46
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357758"
---
# <a name="business-activity-monitoring-bam"></a>业务活动监视 (BAM)
下图说明了业务活动监视 (BAM) 功能的体系结构。  
  
 ![](../core/media/architecture-bam-01.gif "architecture_bam_01")  
  
## <a name="tools"></a>工具  
 可以使用以下工具来设计、 开发和部署 BizTalk 解决方案与 BAM 相集成。  
  
-   **Microsoft Excel**。 BAM 外接程序 excel 提供了指导业务分析员完成活动和视图的创建过程的用户界面。 Excel 可作为用于业务分析师的设计工具和业务用户的数据使用工具。 有关 BAM 外接程序 excel 的详细信息，请参阅[使用 excel BAM 外接程序的要求](../core/requirements-for-using-the-bam-add-in-for-excel.md)。  
  
-   **BAM 管理实用程序**。 BAM 管理实用程序是一种部署工具，允许在工作簿部署到企业中创建的 BAM 定义。 BAM 管理实用程序创建必需的 SQL Server 数据库、 Analysis Services 多维数据集、 SQL Notification Services 数据库和 DTS 或 SSIS 任务 （具体取决于哪个版本的 SQL Server 安装）。 有关 BAM 管理器的详细信息，请参阅[BAM 管理实用程序](../core/bam-management-utility.md)。  
  
-   **跟踪配置文件编辑器**。 跟踪配置文件编辑器，BizTalk 开发人员将映射到包括业务流程的 BizTalk 实现业务分析员定义的数据元素和消息传送。 有关跟踪配置文件编辑器的详细信息，请参阅[跟踪配置文件编辑器](../core/tracking-profile-editor.md)。  
  
-   **跟踪配置文件部署实用程序**。 跟踪配置文件部署实用程序允许 IT 专业人员将新的和更新跟踪配置文件部署到 BAM 基础结构。 有关跟踪配置文件部署工具的详细信息，请参阅[跟踪配置文件部署实用程序](../core/tracking-profile-deployment-utility.md)。  
  
## <a name="presentation"></a>表示形式  
 表示层包括：  
  
- **BAM 门户**。 Microsoft 中的 BAM 门户[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供向业务流程的实时、 端到端可见性。 它是集合的基于 Web 的功能，它包含的 ASP.NET 页。 您可以自定义 BAM 以提高性能和用户体验。 有关 BAM 门户的详细信息，请参阅[BAM 门户](../core/bam-portal.md)。  
  
- **Microsoft Excel**。 BAM 外接程序 excel 提供了指导业务分析员完成活动和视图的创建过程的用户界面。 Excel 可作为用于业务分析师的设计工具和业务用户的数据使用工具。 有关 BAM 外接程序 excel 的详细信息，请参阅[使用 excel BAM 外接程序的要求](../core/requirements-for-using-the-bam-add-in-for-excel.md)。  
  
- **自定义用户界面**。 ISV 和开发人员可以创建显示 BAM 数据的自定义应用程序  
  
## <a name="processing"></a>处理  
 处理层包括：  
  
- **BAM 管理 Web Service**。 BAM 门户应用程序使用此 Web 服务进行通信与 BAM 主导入表 (PIT)。 完成与数据库之间的通信使用的模拟凭据存储在配置期间创建的注册表中。 此 Web 服务公开的方法自定义客户端可以用于获取视图及其详细信息、 相关的活动和数据透视表布局的任何用户。 它们还可以用于管理数据库中的警报。  
  
- **事件总线**。 BAM 事件总线服务处理存储在源数据库中的跟踪数据 （流） 并将目标数据库中以查询表格式数据持续。  
  
- **SQL Notification Services**。 SQL Notification Services 可评估由业务用户定义的实例和聚合 BAM 警报。  
  
  下图演示了 BAM 结构的基础物理流程。  
  
  ![](../core/media/architecture-bam-02.gif "architecture_bam_02")  
  
## <a name="design-time-experience"></a>设计时体验  
 下图说明了设计时体验。  
  
 ![](../core/media/architecture-bam-03.gif "architecture_bam_03")  
  
 以下步骤描述上图中所示的序列。  
  
1.  跟踪配置文件编辑器假定 BizTalk Server 配置、 该至少一个 BAM 定义已部署 （使用 BM.exe） 和基础结构，包括主导入数据库已创建了。 跟踪配置文件编辑器使用在 BizTalk 配置过程中设置来确定管理数据库所在的位置的注册表项。  
  
    1.  BAM 一旦发现枚举主导入数据库中的活动。 BizTalk 开发人员选择从 BAM 主导入数据库中获取请求的已部署的活动。  
  
    2.  BizTalk 开发人员将其映射到物理实现通过浏览从 BizTalk 管理数据库中检索的已部署程序集。  
  
    3.  一旦开发人员具有直观地将此项映射到 BizTalk 项目，元数据提交到 BizTalk Server 运行时，收集和存储数据。 这是通过批注 （对于消息传送用于解码已收集的数据的信息） 和跟踪配置文件 （用来检索运行时数据）。  
  
2.  Microsoft Excel 用作设计时工具和数据使用或表示工具。 设计时 Excel 体验，用户可以通过创建 BAM 活动和视图构造 BAM 定义。 它还允许创建数据透视控件和最终显示在 BAM 门户中的关系图。  
  
## <a name="deployment"></a>部署  
 有两个类别的部署  
  
- 构建动态基础结构  
  
- 检测运行时收集数据。  
  
  下图显示了 BAM 部署。  
  
  ![](../core/media/architecture-bam-04.gif "architecture_bam_04")  
  
  以下步骤描述上图中所示的序列。  
  
1.  BAM 管理实用程序用于构建动态基础结构。 使用 BAM 定义或设计时 Excel 工作簿以及 BAM 配置 XML 文件，BAM 管理实用程序将生成所有必需的数据库和系统运行所需的相应 DTS 或 SSIS 任务。  
  
    1.  BAM 主导入数据库和所有支持存储过程、 触发器以及 DTS 或 SSIS 任务构造。  
  
    2.  BAM 存档数据库定义，但未创建，直到执行存档 DTS 或 SSIS 任务。  
  
    3.  如果定义了 BAM OLAP 聚合，则 BAM 星型架构数据库。 您可以确定是否是否已定义聚合**实时聚合**Excel 电子表格中的按钮处于禁用状态或**CreateOlapCube**设置为**true**中BAM 定义和配置 XML 文件具有一个部署单元，以便**AnalysisDatabase**。  
  
    4.  BAM 定义和配置 XML 必须不是 RTA 的 BAM OLAP 多维数据集创建的聚合定义。  
  
    5.  BAM 管理器进程的分解视图显示了名为 Notification Services 进程 (nscontrol.exe) 以创建 SQL NS 数据库。  
  
2.  跟踪配置文件编辑器用户界面已检测运行时进行跟踪和解码来自运行时系统的数据的部署命令。 在这种情况下它会促使**批注**到 BAM 主导入数据库 （如果将数据从消息传送系统请求）。 跟踪配置文件插入到的 BizTalk 管理数据库的 BizTalk 运行时用于确定要将发布到 BAM 系统的数据。  
  
3.  BizTalk 跟踪部署命令行工具允许跟踪配置文件，以发布到 BAM 主导入数据库和管理数据库，这类似于跟踪配置文件编辑器的作用;但是命令行工具不允许映射功能。  
  
## <a name="data-consumption"></a>数据使用  
 数据流量消耗是指在其中业务用户将使用 BAM 基础结构已收集的信息的过程。 假定此时，已创建了 BAM 定义 (定义哪些数据收集以及如何查看它)、 已部署 BAM 定义 （动态地创建基础结构） 和 BAM 定义已映射到物理实现 (定义从中收集数据，在某些情况下编写代码以推送至系统)。  
  
 下图说明了数据使用的过程。  
  
 ![](../core/media/architecture-bam-05.gif "architecture_bam_05")  
  
 以下步骤描述上图中所示的序列。  
  
1.  BAM 门户将拆分为两个进程、 Internet Explorer 和 Internet 信息服务中托管的 BAM Web 门户进程。  
  
    1.  Internet Explorer 使用连接到 BAM 门户网站的业务用户的安全上下文。 BAM 门户网站是使用 BAM 管理 Web 服务来收集信息的 ASPX 应用程序。  
  
    2.  BAM 门户调用 BAM 管理 Web 服务来检索特定的业务用户可以看到信息如哪些 BAM 活动/视图。 很重要，BAM 管理 Web 服务是能够模拟业务用户，因此，典型部署应是 BAM 门户和 Web 服务托管在同一台计算机上  
  
        > [!NOTE]
        >  如果您的企业支持 Kerberos 和 Active Directory 设置为支持委派，就可以在门户和 Web 服务可以位于不同的计算机上。  
  
    3.  Web 服务调用存储的过程在 BAM 主导入数据库执行安全检查、 检索元数据，以及检索 BAM 实时聚合有关的信息。  
  
        > [!NOTE]
        >  BAM 门户使用名为的未记录的 Web 服务的当前**查询 Web 服务**。 这不受支持，很可能将在下一版本中弃用。  
  
    4.  Internet Explorer 承载 Office Web 控件 (OWC) 的直接连接到 BAM Analysis Services 多维数据集。  
  
2.  “导出”  
  
## <a name="runtime"></a>运行时  
 已定义了 BAM 定义，基础结构已构建，并且开发人员已测试所需系统启用可见性后，数据可以开始源源不断地流经整个系统。  
  
### <a name="data-insertion"></a>插入数据  
 一种主要方式数据流入 BAM 系统是通过 BizTalk 服务 (BTSNTSvc.exe)。 BizTalk 服务的体系结构，以便它可以包含逻辑子系统。  
  
 下图说明了此过程。  
  
 ![](../core/media/architecture-bam-06.gif "architecture_bam_06")  
  
 以下步骤描述上图中所示的序列。  
  
1.  一个子系统托管 BizTalk Server 引擎本身。 此引擎是负责执行业务流程和消息传送。  
  
2.  另一个子系统为事件总线服务。 事件总线服务负责缓冲事件 Stream 数据写入 BAM 主导入数据库。  
  
### <a name="booting-the-runtime"></a>启动运行时  
 BizTalk 服务启动时，每个子系统都会加载该子系统运行所需的元数据。  
  
 下图说明了此过程。  
  
 ![](../core/media/architecture-bam-07.gif "architecture_bam_07")  
  
 以下步骤描述上图中所示的序列。  
  
1.  何时执行 BizTalk 引擎 （业务流程或消息传送），它调用规定数据从该引擎流入 BAM 的侦听器。 在该引擎调用侦听器时，侦听器分析引擎所处的位置相对于业务流程或消息传送项目的执行顺序。 如果需要从当前正在执行引擎的位置检索的数据，则侦听器将收集相应的数据。 确定需要捕获数据和哪些数据需捕获的元数据位于跟踪配置文件。 启动 BizTalk 服务，期间引擎的侦听器将与 BizTalk 管理数据库中提取适当的跟踪配置文件要执行的项目。  
  
2.  事件总线服务的主要功能是将数据 blob （由 BizTalk 引擎写入） 转换为可用数据项，并将数据插入 BAM 主导入数据库。 消息传送侦听器将原始数据写入的压缩形式。 这样做是为了避免大型内存工作集。 为了使事件总线服务将消息传送数据转换为可用数据项，则必须首先加载可解释原始数据的元数据。 此元数据被称为**批注**。 将批注元数据放置在此处通过跟踪配置文件编辑器或命令行跟踪配置文件部署工具。 如果部署的解决方案不会检索与消息传递的数据将不会有任何批注。 业务流程侦听器编码事件总线服务进行正确解码而无需附加的批注的原始窗体中的信息不足。  
  
### <a name="storing-data"></a>将数据存储  
 本部分讨论如何从 BizTalk 服务捕获数据。  
  
 下图说明了此过程。  
  
 ![](../core/media/architecture-bam-08.gif "architecture_bam_08")  
  
 以下步骤描述上图中所示的序列。  
  
1.  BizTalk 引擎，如前所述，已在运行时执行的业务流程和消息传送解决方案期间调用的侦听器。 根据跟踪配置文件信息，侦听器将确定要捕获并将其发送给 BizTalk MessageBox 以二进制形式的数据。 没有用于保存序列化 blob 数据在运行时期间捕获的 TrackingData 表。 在处理期间，有些的时候需要时在执行期间在内存中存储它所持有的数据引擎。 这些参数称为持久化点，而引擎将决定这些点何时发生。 当在发生持久化点时，从侦听器捕获的数据还刷新和持久保存在同一事务中。 这可确保引擎和最终 BAM 可以看到哪些内容中的数据的一致性。 如果发生故障并且事务回滚后，关联的 BAM 数据将也会回滚工作。  
  
2.  事件总线服务位于相同的可执行进程引擎。 该服务从 BTS 引擎 （或任何 BufferedEventStream 数据源） 存储的 TrackingData 表中的数据源。 该图将介绍程序集 – Microsoft.BizTalk.Bam.EventObservation。 此程序集不公开从 BufferedEventStream 检索数据的方法。 此代码位于事件总线服务本身。 检索，然后准备将其存储在主导入数据库数据。 大多数情况下，二进制数据是序列化的.NET 对象解除其冻结之后该属性将移动从对象到带格式的 SQL 语句。  
  
3.  存储数据时，事件总线服务尝试将大型批处理。 批处理包含对生成的 Bam 管理器部署工具的存储过程的调用。 由于大量的数据库活动或其他表锁定的情况下，批处理存储可能会失败。 出现故障时，批处理，则尝试若干次。 如果重试失败，批是拆分成较小的批，且重试。 如果此操作失败，则该批将移至 FailedTracking 表中。  
  
### <a name="custom-data-insertion"></a>自定义数据插入操作  
 上一节演示了如何 BAM 从 BizTalk Server 主机使用各种不同的方法检索数据的详细信息。 间接使用跟踪配置文件编辑器创建一个配置文件，并更直接地使用事件 Stream 方法直接在代码中。 但是，并非所有与 BAM 相关的数据是在 BizTalk 中一定可用。 因此没有可用于自定义编写的应用程序的程序集。  
  
 下图说明了此过程。  
  
 ![](../core/media/architecture-bam-09.gif "architecture_bam_09")  
  
 以下步骤描述上图中所示的序列。  
  
1.  自定义应用程序必须能够加载[Microsoft.BizTalk.Bam.EventObservation](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.aspx)程序集访问的数据插入 BAM 活动的 BAM 方法。 有两个主要类公开，DirectEventStream 和 BufferedEventStream。 上图中突出显示 DirectEventStream 类。 此类将直接写入主导入数据库。 这是数据写入 BAM 活动的最常见方法。  
  
2.  与 BizTalk 用于存储数据的方法相似，BufferedEventStream 类将二进制 blob 写入间接数据库。 在这种情况下，BizTalk MessageBox 用作中间存储。 你选择哪个类取决于几件事情;但是性能是主要考虑因素。 BufferedEventStream 类将数据进行批处理并保持更高的吞吐量。 缺点是不能直接写入数据。  
  
3.  与 BizTalk 方法一样插入数据的事件总线服务将处理的二进制数据、 解码，并最终将其存储在 BAM 主导入数据库中。 这只是数据通过 BufferedEventStream 类写入所必需的。  
  
## <a name="distributed-navigation"></a>分布式的导航  
 BAM 门户分布式的导航功能允许用户跨远程边界查看活动关系。  
  
## <a name="see-also"></a>请参阅  
 [管理和跟踪体系结构](../core/management-and-tracking-architecture.md)