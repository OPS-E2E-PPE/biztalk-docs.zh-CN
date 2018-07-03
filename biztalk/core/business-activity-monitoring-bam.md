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
ms.openlocfilehash: 258294a8a51e6f8e80e360668123e522acf6ff15
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972302"
---
# <a name="business-activity-monitoring-bam"></a>业务活动监视 (BAM)
下图显示了业务活动监视 (BAM) 功能的结构：  
  
 ![](../core/media/architecture-bam-01.gif "architecture_bam_01")  
  
## <a name="tools"></a>工具  
 您可以使用以下工具设计、开发和部署与 BAM 相集成的 BizTalk 解决方案：  
  
-   **Microsoft Excel**。 用于 Excel 的 BAM 加载项提供的用户界面可以指导业务分析员完成活动和视图的创建过程。 Excel 既可用作业务分析员的设计工具，也可用作业务用户的数据使用工具。 有关 BAM 外接程序 excel 的详细信息，请参阅[使用 excel BAM 外接程序的要求](../core/requirements-for-using-the-bam-add-in-for-excel.md)。  
  
-   **BAM 管理实用程序**。 BAM 管理实用程序是一种部署工具，通过该工具，可以将 Excel 中创建的 BAM 定义部署到企业中。 BAM 管理实用程序可创建必需的 SQL Server 数据库、Analysis Services 多维数据集、SQL Notification Services 数据库以及 DTS 或 SSIS 任务（取决于安装的 SQL Server 的版本）。 有关 BAM 管理器的详细信息，请参阅[BAM 管理实用程序](../core/bam-management-utility.md)。  
  
-   **跟踪配置文件编辑器**。 通过跟踪配置文件编辑器，BizTalk 开发人员可以将业务分析员定义的数据元素映射到包含业务流程和消息传送的 BizTalk 实现中。 有关跟踪配置文件编辑器的详细信息，请参阅[跟踪配置文件编辑器](../core/tracking-profile-editor.md)。  
  
-   **跟踪配置文件部署实用程序**。 通过跟踪配置文件部署实用程序，IT 专业人员可将新跟踪配置文件和更新的跟踪配置文件部署到 BAM 基础结构中。 有关跟踪配置文件部署工具的详细信息，请参阅[跟踪配置文件部署实用程序](../core/tracking-profile-deployment-utility.md)。  
  
## <a name="presentation"></a>表示形式  
 表示层包括：  
  
- **BAM 门户**。 Microsoft 中的 BAM 门户[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供向业务流程的实时、 端到端可见性。 它是集合的基于 Web 的功能，它包含的 ASP.NET 页。 您可以自定义 BAM，为用户改善性能和体验。 有关 BAM 门户的详细信息，请参阅[BAM 门户](../core/bam-portal.md)。  
  
- **Microsoft Excel**。 用于 Excel 的 BAM 加载项提供的用户界面可以指导业务分析员完成活动和视图的创建过程。 Excel 既可用作业务分析员的设计工具，也可用作业务用户的数据使用工具。 有关 BAM 外接程序 excel 的详细信息，请参阅[使用 excel BAM 外接程序的要求](../core/requirements-for-using-the-bam-add-in-for-excel.md)。  
  
- **自定义用户界面**。 ISV 和开发人员可以创建用于显示 BAM 数据的自定义应用程序  
  
## <a name="processing"></a>处理  
 处理层包括：  
  
- **BAM 管理 Web Service**。 BAM 门户应用程序使用此 Web 服务进行通信与 BAM 主导入表 (PIT)。 使用配置期间创建的注册表中存储的模拟凭据可以完成与数据库的通信。 此 Web 服务公开的方法自定义客户端可以用于获取视图及其详细信息、 相关的活动和数据透视表布局的任何用户。 还可以将其用于管理数据库中的警报。  
  
- **事件总线**。 BAM 事件总线服务可处理存储于源数据库中的跟踪数据（流），并且以查询表格式将这些数据保存在目标数据库中。  
  
- **SQL Notification Services**。 SQL Notification Services 可评估由业务用户定义的实例和聚合 BAM 警报。  
  
  下图显示了 BAM 结构的基础物理流程。  
  
  ![](../core/media/architecture-bam-02.gif "architecture_bam_02")  
  
## <a name="design-time-experience"></a>设计时体验  
 下图显示了设计时体验：  
  
 ![](../core/media/architecture-bam-03.gif "architecture_bam_03")  
  
 以下步骤介绍了上图中所描述的顺序。  
  
1.  跟踪配置文件编辑器假定 BizTalk Server 已配置，至少部署了一个 BAM 定义（使用 BM.exe），并且包括主导入数据库在内的基础结构已创建。 跟踪配置文件编辑器将使用 BizTalk 配置期间创建的注册表项来确定管理数据库所处的位置。  
  
    1.  BAM 一旦发现主导入数据库，就会枚举该数据库中的活动。 BizTalk 开发人员将选择从 BAM 主导入数据库中请求的已部署活动。  
  
    2.  通过浏览从 BizTalk 管理数据库中检索的已部署程序集，BizTalk 开发人员可以将其映射到物理实现。  
  
    3.  一旦开发人员确实将此项映射到 BizTalk 项目，元数据就会提交到 BizTalk Server 运行时，以收集和存储数据。 这是通过批注（对于用于解码已收集数据的消息传送信息）和跟踪配置文件（用于检索运行时数据）来实现的。  
  
2.  Microsoft Excel 既可用作设计时工具，也可用作数据使用或表示工具。 利用设计时 Excel 体验，用户可以通过创建 BAM 活动和视图来构造 BAM 定义。 并且可以创建最终显示在 BAM 门户中的数据透视控件和图形。  
  
## <a name="deployment"></a>部署  
 存在两种类别的部署  
  
- 构建动态基础结构  
  
- 检测运行时以收集数据。  
  
  下图显示了 BAM 部署：  
  
  ![](../core/media/architecture-bam-04.gif "architecture_bam_04")  
  
  以下步骤介绍了上图中所描述的顺序。  
  
1.  BAM 管理实用程序用于构建动态基础结构。 使用 BAM 定义或设计时 Excel 工作簿以及 BAM 配置 XML 文件，BAM 管理实用程序可以生成所有必需的数据库以及系统运行所需的相应 DTS 或 SSIS 任务。  
  
    1.  构造 BAM 主导入数据库和所有支持的存储过程、触发器以及 DTS 或 SSIS 任务。  
  
    2.  可以定义 BAM 存档数据库，但只有在执行存档 DTS 或 SSIS 任务后，才能创建该数据库。  
  
    3.  如果定义了 BAM OLAP 聚合，则该数据库为 BAM 星型架构数据库。 您可以确定是否是否已定义聚合**实时聚合**Excel 电子表格中的按钮处于禁用状态或**CreateOlapCube**设置为**true**中BAM 定义和配置 XML 文件具有一个部署单元，以便**AnalysisDatabase**。  
  
    4.  必须定义 BAM 定义和配置 XML 的聚合（不是 RTA），以便创建 BAM OLAP 多维数据集。  
  
    5.  BAM 管理器进程的分离型视图显示：调用通知服务进程 (nscontrol.exe) 以创建 SQL NS 数据库。  
  
2.  跟踪配置文件编辑器用户界面具有一个部署命令，该命令可以检测运行时以跟踪和解码来自运行时系统的数据。 在这种情况下它会促使**批注**到 BAM 主导入数据库 （如果将数据从消息传送系统请求）。 跟踪配置文件将插入到由 BizTalk 运行时使用的 BizTalk 管理数据库中以确定要发布到 BAM 系统的数据。  
  
3.  BizTalk 跟踪部署命令行工具允许将跟踪配置文件发布到 BAM 主导入数据库和管理数据库，这一点与跟踪配置文件编辑器的作用相类似；但该命令行工具不支持映射功能。  
  
## <a name="data-consumption"></a>数据使用  
 数据使用表示这样一个进程：在其中，业务用户将使用 BAM 基础结构已收集的信息。 假定此时，BAM 定义已创建（定义要收集哪些数据以及如何查看这些数据）、已部署（动态地创建基础结构）、并已映射到物理实现（定义从何处收集数据，以及在某些情况下将编写代码以推送至系统）。  
  
 下图显示了数据使用的过程：  
  
 ![](../core/media/architecture-bam-05.gif "architecture_bam_05")  
  
 以下步骤介绍了上图中所描述的顺序。  
  
1.  BAM 门户将拆分为两个进程：以 Internet 信息服务为宿主的 Internet Explorer 和 BAM Web 门户进程。  
  
    1.  Internet Explorer 使用连接到 BAM 门户网站的业务用户的安全上下文。 BAM 门户网站是一种使用 BAM 管理 Web Services 收集信息的 ASPX 应用程序。  
  
    2.  BAM 门户调用 BAM 管理 Web Services 来检索信息，例如特定业务用户可查看的 BAM 活动/视图。 BAM 管理 Web Services 能够模拟业务用户是非常重要的，因此，典型部署应是在同一台计算机上承载 BAM 门户和 Web Services。  
  
        > [!NOTE]
        >  如果您的企业支持将 Kerberos 和 Active Directory 设置为支持委托功能，则该门户和 Web Services 可位于不同的计算机上。  
  
    3.  Web Services 可调用 BAM 主导入中的存储过程，以执行安全检查、检索元数据以及检索与 BAM 实时聚合有关的信息。  
  
        > [!NOTE]
        >  BAM 门户使用名为的未记录的 Web 服务的当前**查询 Web 服务**。 现在尚不支持该功能，而且在下一版本中可能会不赞成使用该功能。  
  
    4.  Internet Explorer 是 Office Web Controls (OWC) 的宿主，而后者直接与 BAM Analysis Services 多维数据集进行连接。  
  
2.  “导出”  
  
## <a name="runtime"></a>运行时  
 在定义了 BAM 定义、基础结构已构建完成以及开发人员已测试所需系统启用可见性功能后，数据就可以开始在系统中进行传输了。  
  
### <a name="data-insertion"></a>插入数据  
 数据流入 BAM 系统的主要方法之一就是通过 BizTalk 服务 (BTSNTSvc.exe)。 设计 BizTalk 服务的结构，以便它可以包含逻辑子系统。  
  
 下图对此过程进行了说明：  
  
 ![](../core/media/architecture-bam-06.gif "architecture_bam_06")  
  
 以下步骤介绍了上图中所描述的顺序。  
  
1.  一个子系统将作为 BizTalk Server 引擎本身的宿主。 而该引擎负责执行业务流程和消息传送。  
  
2.  另一个子系统为事件总线服务。 而该事件总线服务负责将已缓冲的事件流数据写入 BAM 主导入数据库中。  
  
### <a name="booting-the-runtime"></a>启动运行时  
 在启动 BizTalk 服务时，每个子系统都会加载该子系统运行所需的元数据。  
  
 下图对此过程进行了说明：  
  
 ![](../core/media/architecture-bam-07.gif "architecture_bam_07")  
  
 以下步骤介绍了上图中所描述的顺序。  
  
1.  在 BizTalk 引擎执行（业务流程或消息传送）期间，它将调用用于规定数据从该引擎流入 BAM 的侦听器。 在该引擎调用侦听器时，该侦听器将根据业务流程或消息传送项目的执行顺序来分析该引擎所处的位置。 如果需要从当前正执行引擎的位置处检索数据，则侦听器将收集相应的数据。 用于确定需捕获的数据及其捕获位置的元数据存储在跟踪配置文件中。 在 BizTalk 服务启动期间，该引擎的侦听器将与 BizTalk 管理数据库进行联系以为要执行的项目请求相应的跟踪配置文件。  
  
2.  事件总线服务的主要功能是将数据 BLOB（由 BizTalk 引擎写入）转换为可用数据项，并将数据插入 BAM 主导入数据库中。 消息传送侦听器将以压缩格式写入原始数据。 这样就可以避免出现大内存工作集。 若要事件总线服务可将消息传送数据转换为可用数据项，则必须首先加载可解释原始数据的元数据。 此元数据被称为**批注**。 通过跟踪配置文件编辑器或命令行跟踪配置文件部署工具将批注元数据放置在此处。 如果部署的解决方案不检索来自消息传送的数据，则不存在任何批注。 业务流程侦听器将对足够多的信息（以原始格式）进行编码，以便事件总线服务在没有任何附加批注的情况下也可以正确解码。  
  
### <a name="storing-data"></a>存储数据  
 本部分将讨论如何从 BizTalk 服务中捕获数据。  
  
 下图对此过程进行了说明：  
  
 ![](../core/media/architecture-bam-08.gif "architecture_bam_08")  
  
 以下步骤介绍了上图中所描述的顺序。  
  
1.  如前所述，BizTalk 引擎具有在运行时执行业务流程和消息传送解决方案期间调用的侦听器。 根据跟踪配置文件信息，侦听器将确定要捕获的数据，然后将这些数据以二进制的形式发送到 BizTalk MessageBox。 存在一个 TrackingData 表，该表用于保存运行时期间捕获的序列化 BLOB 数据。 在处理期间，有时候引擎需要存储执行期间保存在内存中的数据。 这些时候称为持久化点，而引擎将决定这些点在何时发生。 在发生持久化点时，还将刷新从侦听器捕获的数据，并将这些数据保留在同一事务内。 这将确保引擎中的数据与 BAM 最终可以查看的数据的一致性。 如果发生故障并且事务回滚，则关联的 BAM 数据也将回滚。  
  
2.  事件总线服务与引擎位于同一可执行进程中。 该服务从 BTS 引擎存储的 TrackingData 表（或任何 BufferedEventStream 数据源）中提取数据。 该图将介绍程序集 – Microsoft.BizTalk.Bam.EventObservation。 此程序集不公开从 BufferedEventStream 检索数据的方法。 此代码位于事件总线服务本身。 检索数据，然后准备将其存储于主导入数据库中。 通常，二进制数据为序列化的 .NET 对象，在该对象的属性从其移至已格式化的 SQL 语句后将解除其冻结。  
  
3.  进行数据存储时，事件总线服务尝试使用较大的批。 该批包含对 BAM 管理器部署工具生成的存储过程的调用。 由于大量的数据库活动或其他表锁定的因素，该批可能无法存储。 发生故障时，该批将会重试若干次。 若重试失败，则该批将分为几个更小的批，然后重试。 如果仍然失败，则该批将移至 FailedTracking 表。  
  
### <a name="custom-data-insertion"></a>自定义数据插入  
 上一部分演示了 BAM 如何使用不同的方法从 BizTalk Server 主机中检索数据的详细信息。 其中包括了间接使用跟踪配置文件编辑器来创建配置文件，以及更直接的方法，在代码内直接使用事件流方法。 但是，并非所有与 BAM 相关的数据都一定在 BizTalk 中可用。 因此，存在可用于自定义写入应用程序的程序集。  
  
 下图对此过程进行了说明：  
  
 ![](../core/media/architecture-bam-09.gif "architecture_bam_09")  
  
 以下步骤介绍了上图中所描述的顺序。  
  
1.  自定义应用程序必须能够加载[Microsoft.BizTalk.Bam.EventObservation](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.aspx)程序集访问的数据插入 BAM 活动的 BAM 方法。 存在两种已公开的主要类：DirectEventStream 和 BufferedEventStream。 上图中，重点介绍了 DirectEventStream 类。 此类是直接写入主导入数据库的。 这是将数据写入 BAM 活动的最常用的方法。  
  
2.  与 BizTalk 用于存储数据的方法相似，BufferedEventStream 类将二进制 BLOB 写入间接数据库。 在这种情况下，BizTalk MessageBox 用作中间存储。 您所选择的类取决于若干条件；但性能是主要考虑因素。 BufferedEventStream 类将对数据进行批处理并保持较高的吞吐量。 但其不足之处在于，数据不能直接写入。  
  
3.  与用于插入数据的 BizTalk 方法一样，事件总线服务将处理二进制数据，对其进行解码，并最终将其存储在 BAM 主导入数据库中。 上述过程仅对于通过 BufferedEventStream 类写入数据是必需的。  
  
## <a name="distributed-navigation"></a>分布式导航  
 用户使用 BAM 门户的分布式导航功能可以跨远程边界查看活动关系。  
  
## <a name="see-also"></a>请参阅  
 [管理和跟踪体系结构](../core/management-and-tracking-architecture.md)