---
title: BizTalk Server 如何处理大消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 62c070be-dff5-4349-9e36-dd3a7caf1752
caps.latest.revision: 33
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e9d2d31163dcb49861b1cdb6331579502960b6e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387479"
---
# <a name="how-biztalk-server-processes-large-messages"></a>BizTalk Server 如何处理大消息
## <a name="what-is-a-large-message"></a>什么是大消息？  
 遗憾的是，此问题的答案而不能局限于特定的消息大小直接，取决于您的 Microsoft 的特定瓶颈[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]系统。 与大消息相关的问题可以分为以下类别：  
  
-   **内存不足错误**某些类型的消息处理-例如映射、 验证和属性升级的整个消息加载到内存中。 如果在内存中消息的大小超出了可用资源，则会发生内存不足错误。 属于此类别的消息大小阈值是未加载到内存中的消息大小阈值要低得多。 例如，10 MB 平面文件，是解析为 XML，然后映射可能会增长到原来的 10 或更多占用多于 100 MB 的内存，而 100 MB 的 XML 文档，它是未解析或映射实际上只占用 1 MB 的内存，因为它保存到 MessageBox 数据库中。  
  
-   **未加载到内存中的消息的性能问题**不需要加载到内存的消息保存到 MessageBox 数据库使用.NET XmlReader 接口。 虽然它们不受约束必须加载到内存的消息的大小限制，有几个重要因素影响 BizTalk Server 如何处理消息传输到 MessageBox 数据库。  
  
## <a name="factors-that-affect-the-processing-of-large-messages"></a>因素会影响处理大消息  
 原始消息大小、 消息格式和消息处理所有的类型会影响 BizTalk Server 如何处理大消息。  
  
- **原始消息大小**由 BizTalk Server 接收的消息的大小是多大消息时，将 BizTalk Server 处理的最明显的指示。 如果整个消息加载到内存比消息流式传输到 MessageBox 数据库，一条消息的原始大小有很多更大的影响性能。  
  
- **消息格式**消息接收到 BizTalk Server 在两种主要格式之一：XML 文件或平面文件。  
  
  -   **XML 文件**使 BizTalk Server 以执行任何处理而不是直通路由的消息，消息必须采用 XML 文件格式。 如果要处理的文件以 XML 格式接收，则大多数情况下，他们将保留其原始大小。  
  
  -   **平面文件**BizTalk Server 可以执行任何处理而不是直通路由之前，必须为 XML 格式解析平面文件。 将平面文件解析到一个 XML 文件可以极大地增加文件的大小。 平面文件不包含有关其数据的描述性信息的 XML 标记。 XML 文件，但是，包装其所有数据在描述性 XML 标记。 在某些情况下分析可以将大小增加的平面文件的文件的 XML 标记中包含的 10 个或多个，具体取决于多少描述性数据的因素。  
  
  -   **平面文件文档包装在 XML 文档中的单个 CDATA 部分节点**这种类型的文档是 XML 和平面文件的组合，并且可能会产生问题，因为 BizTalk Server 必须将整个包装的平面文件文档加载到内存之前处理它。  
  
- **消息的处理类型**在 BizTalk Server 中，有两种类型的消息处理：仅路由和映射。 绑定到的消息处理的类型的性能变量执行包括消息大小以及是否将消息加载到内存。  
  
  - **仅路由**如果 BizTalk Server 仅用于仅消息路由基于升级的消息属性，则消息进行流式处理到 Messagebox 数据库中使用.NET XmlReader 接口和消息部分都不是单独加载到内存。 在此方案中，内存不足错误不是问题和主要考虑因素是需要非常大的消息 (大于 100 MB) 写入 Messagebox 数据库的时间量。 执行仅路由时，BizTalk Server 开发团队已成功测试了处理的消息最多 1 GB 的大小。  
  
     确定在此方案中性能的主要因素是**大消息片段大小**用于将数据分段到数据库。 **大消息片段大小**上是一个可配置选项**BizTalk 组属性**配置页上，默认值为 102400 字节 (100 KB)。 增加此值可减少流式传输到 MessageBox 数据库中的一条消息所需的往返的次数。  
  
  - **映射**使用映射转换文档可能是占用大量内存的操作。 当通过映射转换文档时，BizTalk Server 将消息传递到.Net XSLCompileTransform 类，以加载 XSL 样式表。 Load 方法成功完成后，调用 Transform 方法可以同时从多个线程。 [XslCompiledTransform 类](http://go.microsoft.com/fwlink/p/?LinkID=282683)XSLCompiledTransform 类提供了详细信息。  
  
     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 通过实现在转换过程将文档加载到内存的可配置的消息大小阈值可显著提高大型文档的内存管理。 低于此阈值大小的任何消息处理在内存中;任何消息，高于此阈值大小且缓冲到文件系统，从而减少内存需求。 默认消息大小阈值为 1 MB。  
  
## <a name="guidelines-for-processing-large-messages"></a>处理大消息的指导原则  
 请遵循以下准则来提高性能，处理大消息在 BizTalk Server 中的时：  
  
1. 调整消息大小阈值，高于此文档将缓冲到文件系统映射过程。 若要修改大小阈值，请创建一个名为**TransformThreshold**中 BizTalk Server 注册表的以下位置：  
  
   ```  
   HKLM\Software\Microsoft\BizTalk Server\3.0\Administration\TransformThreshold  
   ```  
  
    创建此值后，输入要设置为新阈值的字节数的十进制值。 例如，输入十进制值 2097152 可增加到 2 MB 的消息大小阈值 （从 1 MB 的默认值）。 增大此值在具有大量的可用内存来提高吞吐量的系统上。 将文档缓存到磁盘，从而节约内存在整体吞吐量会产生费用。  
  
   > [!NOTE]
   >  默认情况下，在映射期间缓冲到文件系统中的文档会写入到 *%temp%* BizTalk Server 计算机的目录。 更改的设置 *%temp%* 环境变量为非系统磁盘，以提高大型消息缓存到文件系统映射过程时的性能。  
  
2. 最小化使用业务流程中的映射：  
  
   -   如果使用映射来提取或设置与一起使用的属性在业务流程中的业务逻辑使用可分辨的字段，或升级属性进行替代。 提取或设置一个带有地图的值时在文档加载到内存。 当使用可分辨字段或升级的属性时，业务流程引擎访问消息上下文，并不会将文档加载到内存中。  
  
   -   如果您使用映射将多个字段聚合为一个字段，请使用可分辨的字段或升级的属性与业务流程变量累积的结果集。  
  
   -   不要配置具有多个输入转换形状的业务流程。 包含多个输入转换形状的业务流程将不会流入到文件系统映射时。 此限制将导致整个映射加载到内存中，如果文档大小超过指定的 TransformThreshold 注册表值的文档。 一个可能与此问题的解决方法是，将转换在接收端口级别，以便该业务流程不会接受多个转换形状的单个输入。  
  
3. 调整**大消息片段大小**属性上公开**BizTalk 组属性**配置页：  
  
    如果收到的消息的内存中大小超过指定的字节数**大消息片段大小**则消息将拆分为指定大小的片段并片段写入 MessageBox 下按如下所示在 Microsoft 分布式事务处理协调器 (MSDTC) 事务的上下文：  
  
   1.  如果现有的 MSDTC 事务的上下文正在发布传入消息，然后使用此事务的消息片段写入 MessageBox 时。 例如，如果配置为需要事务，则写入消息时，将使用现有事务的事务性适配器正在发布传入消息片段到 MessageBox。  
  
   2.  如果现有的 MSDTC 事务的上下文不正在发布传入消息，然后被创建新的 MSDTC 事务以写入消息片段。  
  
   -   值增加**大消息片段大小**来降低的频率与大消息被分割为碎片，并减少创建关联的 MSDTC 事务的发生率。 这样应做因为过多使用 MSDTC 事务将极大地影响系统性能。 请注意，增加此值还可以增加使用的可用内存量。  
  
   -   如果花费的时间超过 60 分钟才能将消息写入到 MessageBox，则事务超时时，会发生错误，并使写入消息的尝试失败的最大允许 MSDTC 事务超时，并将回滚。 **大消息片段大小**值应足够大才能在处理非常大的消息时避免出现此问题。 具体取决于可用内存，此值应提高到 1000000 字节的最大值。  
  
   -   在消息中的每个消息片段将创建一个或多个 SQL Server 数据库锁定对 MessageBox 数据库。 当锁的数目超过数十万时，很可能 SQL Server 将启动生成"内存不足"错误。 如果出现此问题，请增加**大消息片段大小**以减少针对 MessageBox 数据库所做的 SQL Server 数据库锁的数目。  
  
4. 请考虑保存 MessageBox 数据库上的 SQL Server 的 64 位版本，如果遇到"内存不足"错误。 可用锁的数目是 64 位版本的 SQL Server 上高得多。  
  
5. 调整**大消息阈值**属性上公开**BizTalk 组属性**配置页：  
  
    为消息批次处理时，如果消息批的内存中大小达到指定的字节数**大消息阈值**则将消息批的已处理部分写入 MessageBox 之前处理消息批的其余部分。 这是在 MSDTC 事务上下文，如下所示：  
  
   1. 如果现有的 MSDTC 事务的上下文在发布消息批，则消息批的处理的部分写入 MessageBox 时也使用此事务。 例如，如果配置为需要事务，然后在现有事务的事务性适配器正在发布传入消息批次将消息批的处理的部分写入 MessageBox 时使用。  
  
   2. 如果现有的 MSDTC 事务的上下文不在发布消息批，然后必须创建一个新的 MSDTC 事务将消息批的部分写入 MessageBox。 使用 MSDTC 事务以确保给定的消息批的部分的所有成功写入到 MessageBox 数据库。  
  
      **大消息阈值**设置为直接应用于消息批，但由于消息批可设置为值 1，因此**大消息阈值**设置还可间接应用于单个消息。 例如当一个消息的消息批超过指定时**大消息阈值**参数则**大消息阈值**实际上仅适用于批处理中的单个消息。  
  
   -   **大消息阈值**应调整参数以缓解用于分批放到 MessageBox 的消息批的 MSDTC 事务的创建。 这样应做因为过多使用 MSDTC 事务将极大地影响系统性能。 使用以下计算来确定哪些的最小值**大消息阈值**设置应以避免创建不必要的 MSDTC 事务：  
  
       ```  
       Batch Size * Average size (in bytes) of each message in the batch after being processed by the receive pipeline < Large message threshold  
       ```  
  
        当以字节为单位的消息批的总大小不超过指定的值**大消息阈值**则无需为 BizTalk 启动 MSDTC 事务将消息分批放到 MessageBox数据库。