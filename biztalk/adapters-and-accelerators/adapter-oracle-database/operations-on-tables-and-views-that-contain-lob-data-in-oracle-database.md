---
title: 对表和视图包含在 Oracle 数据库中的 LOB 数据的操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- data type
- binary file
- UpdateLOB
- ReadLOB
- LOB data types
- NCLOB
- large object
- binary large object
- CLOB
- national character large object
- BFILE
- BLOB
- character large object
ms.assetid: 25afd8c7-8ca3-4855-a231-2bec28c9a5cb
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a35be7008c47e46ca65962d113c4604c1cfad42b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984294"
---
# <a name="operations-on-tables-and-views-that-contain-lob-data-in-oracle-database"></a>对表和视图包含在 Oracle 数据库中的 LOB 数据的操作
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]对 Oracle 大型对象 (LOB) 数据类型提供支持：  
  
- 二进制大型对象 (BLOB)  
  
- 字符大型对象 (CLOB)  
  
- 国家/地区字符大型对象 (NCLOB)  
  
- 二进制文件 (BFILE)。 有关详细信息，请参阅[对包含 BFILE 数据类型的表的操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md)。  
  
  在 Oracle 数据库时，LOB 数据类型用于存储大量数据 (最多为 4 GB)。 LOB 类型支持输入和输出流。  
  
  [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]显示表和视图包含 LOB 列的以下操作：  
  
- **ReadLOB**。 ReadLOB 操作提供的表和包含 BLOB、 CLOB、 NCLOB、 和 BFILE 列的视图。 通过使用 ReadLOB 操作，适配器客户端可以读取数据流形式的 LOB 列中的值。 此操作将 LOB 数据类型列的名称和筛选器字符串作为参数。 适配器客户端必须确保筛选器字符串提取一个匹配行。 如果多个匹配行，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]只返回第一个 （匹配） 行的 LOB 列。  
  
  > [!NOTE]
  >  ReadLOB 操作设计为支持的 WCF 服务模型中的 LOB 数据的输入流。 应使用的表选择操作来读取 WCF 通道模型中的 LOB 数据或[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]解决方案。 有关流式处理的详细信息，请参阅[Oracle 数据库中的 LOB 数据类型的流式处理支持](../../adapters-and-accelerators/adapter-oracle-database/streaming-support-for-lob-data-types-in-oracle-database.md)。  
  
- **UpdateLOB**。 UpdateLOB 操作提供的表和包含 BLOB 和 CLOB、 NCLOB 列的视图。 通过使用 UpdateLOB 操作，适配器客户端可以更新 LOB 列中的值。 此操作使用 LOB 数据类型列名称，筛选器字符串，并 base64binary 编码数据用作参数。 适配器客户端必须确保筛选器字符串提取一个匹配行;否则为[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]引发 XmlReaderParsingException。  
  
  > [!NOTE]
  >  UpdateLOB 操作：  
  > 
  > - BFILE 数据类型不支持。 适配器客户端或者可以使用更新操作。 有关详细信息，请参阅[对包含 BFILE 数据类型的表的操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md)。  
  >   -   必须为事务的一部分执行。 若要确保此操作，请**UseAmbientTransaction**绑定属性必须设置为**True**。 璝惠**UseAmbientTransaction**绑定属性，请参阅[用于 Oracle 数据库配置的绑定属性](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)。  
  
> [!NOTE]
>  ReadLOB 和 UpdateLOB 对单个表行中的单个 LOB 列。 若要在多个行中的 LOB 列或多个 LOB 列中的单个行上运行，必须为每个目标列中每个目标行调用 ReadLOB 或 UpdateLOB。  
  
 有关详细信息：  
  
- 调用上使用 Oracle 数据库表的 UpdateLOB 操作[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[具有通过使用 BizTalk Server 的大型对象类型数据的表上执行操作](https://msdn.microsoft.com/library/cc185405(v=bts.10).aspx)。 (您应使用的表选择操作读取中的 LOB 数据类型[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。)  
  
- 调用一个使用 WCF 服务模型的 Oracle 数据库表上的 ReadLOB 和 UpdateLOB 操作，请参阅[与使用 WCF 服务模型的大型对象类型的表上运行操作](../../adapters-and-accelerators/adapter-sql/read-or-update-tables-and-views-with-large-data-types-in-sql-with-a-wcf-service.md)。  
  
- 消息结构和 SOAP 操作执行 ReadLOB 和 UpdateLOB 操作，请参见[特殊 LOB 操作的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-special-lob-operations2.md)。  
  
## <a name="see-also"></a>请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185259(v=bts.10).aspx)