---
title: BAM API 示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 32a925f2-c7f4-4111-9c59-8865f15c6a89
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4dbc1adba5ef1b0c0a86c456a86ac3cce627d34f
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528533"
---
# <a name="bam-api-biztalk-server-sample"></a>BAM API （BizTalk Server 示例）
BAM API 示例说明了如何将对 BAM API 的调用合并到应用程序以保存可以监视的关键信息。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 此示例实现一个简单的购买方案。 它生成采购订单、 处理每个采购订单、 创建装运并创建和处理发票。 在示例运行时，它将创建并更新 BAM 活动，以反映的详细信息和处置的采购订单和发票。  
  
## <a name="how-this-sample-was-designed-and-why"></a>此示例设计的方式和原因  
 此示例旨在演示了如何使用 BAM 存储不是 BizTalk 业务流程的应用程序中的信息。 简单应用程序时，它说明了可能会在生产应用程序中使用的 BAM 的几个方面。 其中包括：  
  
- 向单个活动分配多个线程  
  
- 创建两个活动之间的关系  
  
- 使用继续功能允许使用不同的 Id 访问同一活动  
  
  BAM API 示例由三个主要类组成： 一个处理采购订单，一个处理发货和一个处理发票。 每个类具有**RunOnce**方法从队列检索消息，然后处理该消息。 每个类还具有**运行**持续调用的方法**RunOnce**方法。  
  
  **RunOnce**方法**PoApplication**类执行以下操作：  
  
1. 创建表示采购订单的 XML 消息。  
  
2. 开始 BAMApiPo 活动，并添加有关采购订单和收到它时的信息。  
  
3. 任意批准或拒绝采购订单。  
  
4. 更新 BAMApiPo 活动以记录采购订单 （接受或拒绝） 的状态。  
  
5. 如果已接受采购订单， **RunOnce**方法还执行以下操作：  
  
   1.  创建 XML 消息，以表示包要寄送，并将消息添加到发货队列。  
  
   2.  将添加到要包含在发票中的采购订单队列表示采购订单的 XML 消息。  
  
   3.  启用 BAMApiPo 活动的继续符。  
  
   4.  结束 BAMApiPo 活动。  
  
   **RunOnce**方法**ShipmentApplication**类执行以下操作：  
  
6. 从其队列中检索代表要发运的货包的 XML 消息。  
  
7. 更新 BAMApiPo 活动以记录货包的时间。  
  
8. 结束 BAMApiPo 活动。  
  
   **RunOnce**方法**InvoiceApplication**类执行以下操作：  
  
9. 从其队列中检索代表开发票的采购订单的 XML 消息。  
  
10. 开始 BAMApiInvoice 活动。  
  
11. 创建 BAM 关系 BAMApiInvoice 活动和 BAMApiPo 活动将要开发票的采购订单之间。  
  
12. 向 BAMApiPo 活动有关的信息和发票时创建它。  
  
13. 在任意延迟模拟等待要付款的发票后, 向 BAMApiInvoice 活动发票支付的时间。  
  
14. 结束 BAMApiInvoice 活动。  
  
    **Main**方法**MainApp**类初始化应用程序。 它执行以下操作：  
  
15. 创建**DirectEventStream**对象。  
  
16. 启动多个线程，并调用**运行**方法**POApplication**中每个线程对象。  
  
17. 启动多个线程，并调用**运行**方法**ShipmentApplication**中每个线程对象。  
  
18. 启动多个线程，并调用**运行**方法**InvoiceApplication**中每个线程对象。  
  
    **Global**类定义一些常量，由示例应用程序，如要创建的线程数和拒绝采购订单的百分比。  
  
    除了 Visual Studio 解决方案中，该示例还包含用于定义活动的 Microsoft Excel 文件。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 您可以找到在此示例*\<示例路径\>* \BAM\BamApiSample。  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|----------|-----------------|  
|BamApiSample.cs|已检测应用程序。|  
|BamApiSample.csproj|已检测应用程序项目。|  
|BamApiSample.sln|检测应用程序解决方案。|  
|BamApiSample.xls|BAM 定义样式表。|  
|Cleanup.bat|若要删除已部署的示例文件的批处理文件。|  
|Input.txt|输入示例侦听器配置。|  
|InterceptorConfig.cs|API 示例的侦听器配置代码。|  
|InterceptorConfig.csproj|侦听器配置项目。|  
|Invoice_config.xml|Invoice 侦听器配置。|  
|Invoice_interceptor.bin|序列化的 invoice 侦听器。|  
|PurchaseOrder_config.xml|PurchaseOrder 侦听器配置。|  
|PurchaseOrder_interceptor.bin|序列化的 PurchaseOrder 侦听器。|  
|Setup.bat|若要部署和登记示例文件的批处理文件。|  
|Shipment_config.xml|Shipment 侦听器配置。|  
|Shipment_interceptor.bin|序列化的 shipment 侦听器。|  
  
## <a name="run-the-bam-api-sample"></a>运行 BAM API 示例  
  
1.  打开命令提示符下以管理员身份，并运行*\<示例路径\>* \BAM\ BamApiSample\setup.bat。  
  
2.  以管理员身份启动 Visual Studio 并打开*\<示例路径\>* BAMAPISAMPLE\BAMAPISAMPLE.SLN 解决方案。 
  
    > [!IMPORTANT]
    >  在行`//#define Interceptor`中 BamApiSample.cs 文件必须注释掉。不要删除"/ /"从该行。 BAM API 示例使用的不是深入了解代码`#if Interceptor`预处理器指令。  
  
3.  生成解决方案。  
  
4.  运行*\<示例路径\>* \BAM\BamApiSample\bin\debug\BamApiSample.exe。  
  
     输出将如下所示：  
  
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
  
5.  后一分钟左右，按 CTRL + C 或关闭命令提示符窗口以停止 BamApiSample 程序。  
  
## <a name="view-the-results"></a>查看结果
  
1.  打开 SQL Server Management Studio。  
  
2.  在 SQL Server Management Studio 中，展开服务器，展开**数据库**，展开**BAMPrimaryImport**，然后展开**表**。  
  
3.  右键单击**dbo.bam_BAMApiInvoice_Active** ，然后单击**打开表**。 如果使用 SQL Server，请单击**选择前 1000年行**。  
  
     Bam_BAMApiInvoice_Active 表的内容显示在右窗格中。 在表中的每一行表示已经启动但尚未完成的 BAMApiInvoice 活动。  
  
4.  右键单击**dbo.bam_BAMApiPo_Completed** ，然后单击**打开表**。 如果使用 SQL Server，请单击**选择前 1000年行**。  
  
     Bam_BAMApiPo_Completed 表的内容显示在右窗格中。 表中的每一行表示已完成的 BAMApiPo 活动。