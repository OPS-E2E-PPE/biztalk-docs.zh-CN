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
ms.openlocfilehash: f17509983e7eab7b8743c8036c429c886b0b9265
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016524"
---
# <a name="how-biztalk-server-processes-large-messages"></a>BizTalk Server 如何处理大消息
## <a name="what-is-a-large-message"></a>什么是大消息？  
 遗憾的是，此问题的答案而不能局限于特定的消息大小直接，取决于您的 Microsoft 的特定瓶颈[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]系统。 与大消息关联的问题可分为以下几类：  
  
-   **内存不足错误**某些类型的消息处理-例如映射、 验证和属性升级的整个消息加载到内存中。 如果内存中的消息大小超出了可用资源，则会发生内存不足错误。 与未加载到内存中的消息的大小阈值相比，属于此类别的消息的大小阈值要小得多。 例如，已解析为 XML 并已进行映射的 10 MB 平面文件可能按 10 或更大的因子增大，从而占用多于 100 MB 的内存，然而未进行解析或映射的 100 MB 的 XML 文档实际只需占用 1 MB 的内存，因为它是保存到 MessageBox 数据库中的。  
  
-   **未加载到内存中的消息的性能问题**不需要加载到内存的消息保存到 MessageBox 数据库使用.NET XmlReader 接口。 尽管保存到 MessageBox 数据库的消息不会受限于必须加载到内存中的消息所受到的大小限制，但仍然存在某些重要的因素将影响 BizTalk Server 处理此类消息方式。  
  
## <a name="factors-that-affect-the-processing-of-large-messages"></a>影响处理大消息的因素  
 原始消息大小、消息格式以及消息的处理类型都会影响 BizTalk Server 处理大消息的方式。  
  
- **原始消息大小**由 BizTalk Server 接收的消息的大小是多大消息时，将 BizTalk Server 处理的最明显的指示。 在整个消息加载到内存的情况下，消息的原始大小对性能的影响比在消息保存到 MessageBox 数据库的情况下对性能的影响要大得多。  
  
- **消息格式**消息接收到 BizTalk Server 在两种主要格式之一： XML 文件或平面文件。  
  
  -   **XML 文件**使 BizTalk Server 以执行任何处理而不是直通路由的消息，消息必须采用 XML 文件格式。 如果要处理的文件是以 XML 格式接收的，则这些文件将在很大程度上保留其原始大小。  
  
  -   **平面文件**BizTalk Server 可以执行任何处理而不是直通路由之前，必须为 XML 格式解析平面文件。 将平面文件解析为 XML 文件将极大地增加文件大小。 因为平面文件不包含带有关于其数据的描述性信息的 XML 标记。 另一方面，XML 文件还在描述性 XML 标记中包装了其所有数据。 在某些情况下，解析操作会按 10 或更大的因子增加平面文件的大小，具体取决于该文件的 XML 标记中包含的描述性数据的数量。  
  
  -   **平面文件文档包装在 XML 文档中的单个 CDATA 部分节点**这种类型的文档是 XML 和平面文件的组合，并且可能会产生问题，因为 BizTalk Server 必须将整个包装的平面文件文档加载到内存之前处理它。  
  
- **消息的处理类型**在 BizTalk Server 中，有两种类型的消息处理： 仅路由和映射。 与要执行的消息处理类型相关联的性能变量包括消息大小以及消息是否加载到内存中。  
  
  - **仅路由**如果 BizTalk Server 仅用于仅消息路由基于升级的消息属性，则消息进行流式处理到 Messagebox 数据库中使用.NET XmlReader 接口和消息部分都不是单独加载到内存。 在此方案中，不会发生内存不足错误，而需要注意的主要问题是将超大的消息（大于 100 MB）写入 Messagebox 数据库所需的时间。 BizTalk Server 开发小组已成功测试了在执行仅路由处理时可处理高达 1 GB 的消息。  
  
     确定在此方案中性能的主要因素是**大消息片段大小**用于将数据分段到数据库。 **大消息片段大小**上是一个可配置选项**BizTalk 组属性**配置页上，默认值为 102400 字节 (100 KB)。 增大此值会减少将消息保存到 MessageBox 数据库所需的往返次数。  
  
  - **映射**使用映射转换文档可能是占用大量内存的操作。 通过映射转换文档时，BizTalk Server 会将消息传递到 .Net XSLCompileTransform 类，以加载 XSL 样式表。 在 Load 方法成功完成后，可从多个线程同时调用 Transform 方法。 [XslCompiledTransform 类](http://go.microsoft.com/fwlink/p/?LinkID=282683)XSLCompiledTransform 类提供了详细信息。  
  
     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 通过在转换过程中对将文档加载到内存的操作应用可配置消息大小阈值，显著地提高了大文档的内存管理。 所有大小低于此阈值的消息都可在内存中进行处理；而任何大小高于此阈值的消息都将缓冲到文件系统中以减少对内存的需求。 默认的消息大小阈值为 1 MB。  
  
## <a name="guidelines-for-processing-large-messages"></a>处理大消息的准则  
 遵循这些准则，在 BizTalk Server 中处理大消息时可提高性能：  
  
1. 调整消息大小阈值，在映射期间，高于此阈值的文档将缓冲到文件系统中。 若要修改大小阈值，请创建一个名为**TransformThreshold**中 BizTalk Server 注册表的以下位置：  
  
   ```  
   HKLM\Software\Microsoft\BizTalk Server\3.0\Administration\TransformThreshold  
   ```  
  
    创建此值后，请输入一个要设置为新阈值的字节数的十进制值。 例如，输入十进制值 2097152 可将消息大小阈值从默认的 1 MB 增大至 2 MB。 在具有大量可用内存的系统上增大此值可提高吞吐量。 将文档缓存到磁盘可以节省内存，但是会对总体吞吐量造成影响。  
  
   > [!NOTE]
   >  默认情况下，在映射期间缓冲到文件系统中的文档会写入到 *%temp%* BizTalk Server 计算机的目录。 更改的设置 *%temp%* 环境变量为非系统磁盘，以提高大型消息缓存到文件系统映射过程时的性能。  
  
2. 在业务流程中尽量减少使用映射：  
  
   -   如果你在业务流程中正使用映射来提取或设置用于业务逻辑的属性，请使用可分辨字段和升级属性进行替代。 在使用映射提取或设置值时，需要将文档加载到内存中。 但如果使用可分辨字段和升级属性，则业务流程引擎将访问消息上下文，而无需将文档加载到内存中。  
  
   -   如果正在使用映射将多个字段聚合为一个字段，请将可分辨字段或升级属性与业务流程变量结合使用，以累计结果集。  
  
   -   请不要在业务流程中配置具有多个输入的转换形状。 映射时，如果业务流程中包含的转换形状具有多个输入，则该业务流程将不会流入到文件系统中。 如果文档大小超过了指定的 TransformThreshold 注册表值，这种限制会导致将被映射的文档整个加载到内存中。 此问题的一种可能的解决方法是在接收端口级别应用转换，这样业务流程就不会接受多个转换形状输入。  
  
3. 调整**大消息片段大小**属性上公开**BizTalk 组属性**配置页：  
  
    如果收到的消息的内存中大小超过指定的字节数**大消息片段大小**则消息将拆分为指定大小的片段并片段写入 MessageBox 下按如下所示在 Microsoft 分布式事务处理协调器 (MSDTC) 事务的上下文：  
  
   1.  如果正在现有的 MSDTC 事务上下文中发布传入消息，则在消息片段写入 MessageBox 时使用此事务。 例如，如果配置为需要事务的事务性适配器正在发布传入消息，则在消息片段写入 MessageBox 时使用现有事务。  
  
   2.  如果没有在现有的 MSDTC 事务上下文中发布传入消息，则将创建一个新的 MSDTC 事务以写入消息片段。  
  
   -   值增加**大消息片段大小**来降低的频率与大消息被分割为碎片，并减少创建关联的 MSDTC 事务的发生率。 因此应该增大此值，因为过多使用 MSDTC 事务将极大地影响系统性能。 请注意，增大此值还可能增加要使用的可用内存量。  
  
   -   如果将消息写入 MessageBox 所用时间大于最大允许的 MSDTC 事务超时时间（60 分钟），则该事务将超时并显示错误，尝试写入消息的操作失败，并进行回滚。 **大消息片段大小**值应足够大才能在处理非常大的消息时避免出现此问题。 根据可用内存的大小，可将此值提高到 1000000 字节的最大值。  
  
   -   消息中的每个消息片段都可针对 MessageBox 数据库创建一个或多个 SQL Server 数据库锁定。 如果锁定数目超过数十万，则 SQL Server 可能会发生“内存不足”错误。 如果出现此问题，请增加**大消息片段大小**以减少针对 MessageBox 数据库所做的 SQL Server 数据库锁的数目。  
  
4. 如果出现“内存不足”错误，请考虑在 64 位版本的 SQL Server 上保存 MessageBox 数据库。 在 64 位版本的 SQL Server 上，可用锁定的数目将大大增加。  
  
5. 调整**大消息阈值**属性上公开**BizTalk 组属性**配置页：  
  
    为消息批次处理时，如果消息批的内存中大小达到指定的字节数**大消息阈值**则将消息批的已处理部分写入 MessageBox 之前处理消息批的其余部分。 此操作是在 MSDTC 事务的上下文中完成的，如下所示：  
  
   1. 如果正在现有的 MSDTC 事务上下文中发布消息批，则在消息批的已处理部分写入 MessageBox 时使用此事务。 例如，如果配置为需要事务的事务性适配器正在发布传入消息批，则在消息批的已处理部分写入 MessageBox 时使用现有事务。  
  
   2. 如果没有在现有的 MSDTC 事务上下文中发布消息批，则必须创建一个新的 MSDTC 事务以将消息批的各部分写入 MessageBox。 使用 MSDTC 事务可确保给定消息批的所有部分均可成功写入 MessageBox 数据库。  
  
      **大消息阈值**设置为直接应用于消息批，但由于消息批可设置为值 1，因此**大消息阈值**设置还可间接应用于单个消息。 例如当一个消息的消息批超过指定时**大消息阈值**参数则**大消息阈值**实际上仅适用于批处理中的单个消息。  
  
   -   **大消息阈值**应调整参数以缓解用于分批放到 MessageBox 的消息批的 MSDTC 事务的创建。 应该增大此值，因为过多使用 MSDTC 事务将极大地影响系统性能。 使用以下计算来确定哪些的最小值**大消息阈值**设置应以避免创建不必要的 MSDTC 事务：  
  
       ```  
       Batch Size * Average size (in bytes) of each message in the batch after being processed by the receive pipeline < Large message threshold  
       ```  
  
        当以字节为单位的消息批的总大小不超过指定的值**大消息阈值**则无需为 BizTalk 启动 MSDTC 事务将消息分批放到 MessageBox数据库。