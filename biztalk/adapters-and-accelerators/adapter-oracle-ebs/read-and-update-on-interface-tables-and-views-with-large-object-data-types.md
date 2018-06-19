---
title: 对接口表、 界面视图、 表和视图包含 LOB 数据的操作 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0f6e8db6-ba68-4e3f-84b2-1cc31ce89bcb
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b12eeae422f5da90c6874f70d2ffddbc19f75bd
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964699"
---
# <a name="operations-on-interface-tables-interface-views-tables-and-views-that-contain-lob-data"></a>对接口表、 界面视图、 表和视图包含 LOB 数据的操作
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]提供对 Oracle 大型对象 (LOB) 数据类型的支持：  
  
-   二进制大型对象 (BLOB)  
  
-   字符大型对象 (CLOB)  
  
-   国家/地区字符大型对象 (NCLOB)  
  
-   二进制文件 (BFILE)。 有关详细信息，请参阅[对表，包含 BFILE 数据类型操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md)。  
  
 LOB 数据类型用于存储大量数据，在基础的 Oracle 数据库中，最多 4 千兆字节 (GB)。 BFILE 数据类型，除外 LOB 数据类型支持输入和输出流。  

## <a name="operations-for-tables-and-views"></a>表和视图的操作  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]呈现对接口表、 界面视图、 表和视图包含 LOB 列执行以下操作：  
  
-   **Read_\<LOBColName\>**:`Read_<LOBColName>`操作针对接口表、 界面视图、 表和视图包含 BLOB、 CLOB、 NCLOB、 和 BFILE 列，显示其中\<LOBColName\>是 BLOB、 CLOB、 NCLOB 或 BFILE 的类型的列的名称。 通过使用 Read_\<LOBColName\>操作，适配器客户端可以读取数据流形式的 LOB 列中的值。 此操作将作为参数的筛选器字符串。  
  
    > [!NOTE]
    >  `Read_<LOBColName>`操作旨在支持的 WCF 服务模型中的 LOB 数据的输入流。 应使用表选择操作从 WCF 通道模型读取 LOB 数据或[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]解决方案。  
  
-   **Update_\<LOBColName\>**:`Update_<LOBColName>`操作针对接口表和表仅包含 BLOB、 CLOB、 和 NCLOB 列，显示其中\<LOBColName\>是的名称列类型 BLOB、 CLOB、 和 NCLOB。 通过使用 Update_\<LOBColName\>操作，适配器客户端可以更新 LOB 列中的值。 对于 BLOB 数据类型，此操作将 base64binary 编码数据作为参数，而对于 CLOB 和 NCLOB 数据类型，此操作采用字符串筛选器作为参数。  
  
    > [!NOTE]
    >  `Update_<LOBColName>`操作：  
    >   
    >  -   不支持 BFILE 数据类型。 适配器客户端或者可以使用更新操作。 有关详细信息，请参阅[对表，包含 BFILE 数据类型操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md)。  
    > -   不公开的接口视图和视图。  
    > -   必须作为事务的一部分执行。 若要确保此操作，请**UseAmbientTransaction**绑定属性必须设置为**True**。 璝惠**UseAmbientTransaction**绑定属性，请参阅[Rad 有关用于 Oracle E-business Suite 绑定属性的 BizTalk Adapter](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。  
  
> [!IMPORTANT]
>  [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]曲面`Read_<LOBColName>`和`Update_<LOBColName>`为表中每个 LOB 列的操作。 因此，如果表 （LOBCol1 和 LOBCol2） 中有两个 LOB 列，则有两个`Read_<LOBColName>`操作 （Read_LOBCol1 和 Read_LOBCol2） 和两个`Update_<LOBColName>`操作 （Update_LOBCol1 和 Update_LOBCol2）。  
  
## <a name="more-good-info"></a>良好的详细信息  
  
-   调用`Read_<LOBColName>`和`Update_<LOBColName>`在 Oracle E-business Suite 中使用基础数据库中表的操作[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[表与大数据类型使用 BizTalk Server 上运行操作](../../adapters-and-accelerators/adapter-sql/run-operations-on-tables-and-views-with-large-data-types-using-the-sql-adapter.md)。  
  
-   消息结构和用于执行的 SOAP 操作`Read_<LOBColName>`和`Update_<LOBColName>`操作，请参阅[特殊 LOB 操作的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-special-lob-operations1.md)。  
  
## <a name="see-also"></a>另请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)