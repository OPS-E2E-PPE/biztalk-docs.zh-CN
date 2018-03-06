---
title: "BAM API 示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 32a925f2-c7f4-4111-9c59-8865f15c6a89
caps.latest.revision: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e181af5766231ed9a7d828b49e2d840a47f216c
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2018
---
# <a name="bam-api-biztalk-server-sample"></a>BAM API（BizTalk Server 示例）
BAM API 示例显示如何将对 BAM API 的调用合并到应用程序中，以保存可以监视的关键信息。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 本示例用于实现简单的购买方案。 它将生成采购订单、处理每个采购订单、创建装运并创建和处理发票。 在本示例运行时，将创建和更新 BAM 活动，以反映采购订单和发票的详细信息和对它们的处置。  
  
## <a name="how-this-sample-was-designed-and-why"></a>本示例的设计方式和原因  
 本示例旨在说明如何使用 BAM 存储不是来自 BizTalk 业务流程的应用程序提供的信息。 当应用程序比较简单时，将介绍很可能需要在生产应用程序中使用的多个方面的 BAM。 其中包括：  
  
-   向单个活动分配多个线程  
  
-   创建两个活动之间的关系  
  
-   使用继续功能允许通过不同的 ID 访问同一活动  
  
 BAM API 示例由三个主要类组成︰ 一个用于处理采购订单、 处理装运到一个，另一个以处理发票。 每个类具有 **RunOnce** 从队列检索消息，然后处理该消息的方法。 每个类还具有 **运行** 不断地调用的方法 **RunOnce** 方法。  
  
 **RunOnce** 方法 **PoApplication** 类执行下列任务︰  
  
1.  创建表示采购订单的 XML 消息。  
  
2.  开始 BAMApiPo 活动，向获得添加有关采购订单及接收时间的信息。  
  
3.  任意批准或拒绝采购订单。  
  
4.  更新 BAMApiPo 活动以记录采购订单的状态（接受或拒绝）。  
  
5.  如果已接受的采购订单， **RunOnce** 方法还执行以下︰  
  
    1.  创建 XML 消息以代表要发运的货包，并将该消息添加到发货队列。  
  
    2.  将表示采购订单的 XML 消息添加到要包含在发票中的采购订单队列中。  
  
    3.  启用 BAMApiPo 活动的继续。  
  
    4.  结束 BAMApiPo 活动。  
  
 **RunOnce** 方法 **ShipmentApplication** 类执行下列任务︰  
  
1.  从其队列中检索代表要发运的货包的 XML 消息。  
  
2.  更新 BAMApiPo 活动以记录发运货包的时间。  
  
3.  结束 BAMApiPo 活动。  
  
 **RunOnce** 方法 **InvoiceApplication** 类执行下列任务︰  
  
1.  从其队列中检索代表要开发票的采购订单的 XML 消息。  
  
2.  开始 BAMApiInvoice 活动。  
  
3.  为将要开发票的采购订单在 BAMApiInvoice 活动和 BAMApiPo 活动之间创建 BAM 关系。  
  
4.  向 BAMApiPo 活动中添加有关发票和创建时间的信息。  
  
5.  在任意延迟模拟等待要付款的发票之后，向 BAMApiInvoice 活动中添加发票的付款时间。  
  
6.  结束 BAMApiInvoice 活动。  
  
 **Main** 方法 **MainApp** 类初始化应用程序。 它执行以下操作：  
  
1.  创建 **DirectEventStream** 对象。  
  
2.  启动多个线程和调用 **运行** 方法 **POApplication** 中每个线程对象。  
  
3.  启动多个线程和调用 **运行** 方法 **ShipmentApplication** 中每个线程对象。  
  
4.  启动多个线程和调用 **运行** 方法 **InvoiceApplication** 中每个线程对象。  
  
 **全局** 类定义使用的示例应用程序，例如要创建的线程数和要拒绝的采购订单的百分比的常量。  
  
 除了 Visual Studio 解决方案中，该示例还包含定义的活动的 Microsoft Excel 文件。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 你可以找到在此示例*\<示例路径\>*\BAM\BamApiSample。  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|----------|-----------------|  
|BamApiSample.cs|开发的应用程序。|  
|BamApiSample.csproj|开发的应用程序项目。|  
|BamApiSample.sln|开发的应用程序解决方案。|  
|BamApiSample.xls|BAM 定义样式表。|  
|Cleanup.bat|用于删除已部署示例文件的批处理文件。|  
|Input.txt|用于输入示例侦听器配置。|  
|InterceptorConfig.cs|API 示例的侦听器配置代码。|  
|InterceptorConfig.csproj|侦听器配置项目。|  
|Invoice_config.xml|Invoice 侦听器配置。|  
|Invoice_interceptor.bin|序列化的 Invoice 侦听器。|  
|PurchaseOrder_config.xml|PurchaseOrder 侦听器配置。|  
|PurchaseOrder_interceptor.bin|序列化的 PurchaseOrder 侦听器。|  
|Setup.bat|用于部署和登记示例文件的批处理文件。|  
|Shipment_config.xml|Shipment 侦听器配置。|  
|Shipment_interceptor.bin|序列化的 Shipment 侦听器。|  
  
## <a name="run-the-bam-api-sample"></a>运行 BAM API 示例  
  
1.  打开命令提示符以管理员身份，并运行*\<示例路径\>*\BAM\ BamApiSample\setup.bat。  
  
2.  作为管理员，启动 Visual Studio 并打开*\<示例路径\>*\BAM\ BamApiSample\BamApiSample.sln 解决方案。 
  
    > [!IMPORTANT]
    >  必须注释掉 BamApiSample.cs 文件中的行 `//#define Interceptor`。请勿从该行中删除 “//”。 BAM API 示例只使用不在 `#if Interceptor` 的预处理器指令内的代码。  
  
3.  生成解决方案。  
  
4.  运行*\<示例路径\>*\BAM\BamApiSample\bin\debug\BamApiSample.exe。  
  
     输出将如下所示︰  
  
    ```  
    ...  
    New Purchase Order #17 Received  
    8 was shipped as pkg#87  
    New Purchase Order #18 Received.  
    Shipping package pkg#87 via DHL  
    13 was Approved.  
    18 was Rejected.  
    17 was Rejected.  
    11 was shipped as pkg#114  
    16 wsas Rejected.  
    Shipping package pkg#114 via DHL  
    Invoice #5 send for {2 5 1 9 4 8 11 }  
    Package pkg#49 was delivered  
    New Purchase Order #19 Received.  
    ...  
    ```  
  
5.  在大约一分钟后，按 Ctrl+C 或关闭命令提示符窗口，以停止 BamApiSample 程序。  
  
## <a name="view-the-results"></a>查看结果
  
1.  打开 SQL Server Management Studio。  
  
2.  在 SQL Server Management Studio，展开服务器，展开 **数据库**, ，展开 **BAMPrimaryImport**, ，然后展开 **表**。  
  
3.  右键单击 **dbo.bam_BAMApiInvoice_Active** ，然后单击 **打开表**。 如果你使用的 SQL Server，请单击**选择前 1000年行**。  
  
     bam_BAMApiInvoice_Active 表的内容将显示在右窗格中。 表中的每行均表示已经启动但尚未完成的 BAMApiInvoice 活动。  
  
4.  右键单击 **dbo.bam_BAMApiPo_Completed** ，然后单击 **打开表**。 如果你使用的 SQL Server，请单击**选择前 1000年行**。  
  
     bam_BAMApiPo_Completed 表的内容将显示在右窗格中。 表中的每行均表示已完成的 BAMApiPo 活动。