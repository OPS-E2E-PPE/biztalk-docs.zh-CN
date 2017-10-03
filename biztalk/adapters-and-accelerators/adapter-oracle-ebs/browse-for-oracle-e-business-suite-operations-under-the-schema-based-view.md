---
title: "用于 Oracle E-business Suite 操作基于架构的视图下浏览 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d004a99f-0db1-4cdb-80cd-ea71de4e1098
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e3dea968a12470498012f7dae4fb3093fc05e59
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="browse-for-oracle-e-business-suite-operations-under-the-schema-based-view"></a>用于 Oracle E-business Suite 操作基于架构的视图下浏览
你可以使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]若要浏览的出站和入站操作，可以对 Oracle E-business Suite 执行使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 本主题提供有关如何浏览基于架构的视图下的出站和入站操作的信息。  
  
> [!NOTE]
>  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]和[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]当您浏览和搜索操作，因此相同的主题中所述两个组件时所显示实质上是相同的接口。  
  
## <a name="prerequisites"></a>先决条件  
 你可以浏览元数据的目标操作之前，你必须连接到 Oracle E-business Suite。 有关如何连接到 Oracle 数据库使用时[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，请参阅[连接到 Visual Studio 中 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)。  
  
## <a name="browsing-for-outbound-operations"></a>为出站操作浏览  
 执行以下步骤以浏览基于架构的视图下的出站操作。  
  
#### <a name="to-browse-metadata-for-outbound-operations-under-the-schema-based-view"></a>若要浏览基于架构的视图下的出站操作的元数据  
  
1.  连接到 Oracle E-business Suite 使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 请参阅[连接到 Visual Studio 中 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)有关的说明。  
  
2.  从**选择协定类型**列出，请为出站操作选择**客户端 （出站操作）**。  
  
3.  **选择类别**框中列出的在其下的 Oracle E-business Suite 项目进行分类的不同视图。  
  
     下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 选择根节点 （/），并且中列出了可用的根节点下的常规类别节点**可用类别和操作**框。  
  
     ![操作和在根级别的类别](../../adapters-and-accelerators/adapter-oracle-ebs/media/559a6652-2d9d-4ecd-a1bb-4f63750c9518.gif "559a6652-2d9d-4ecd-a1bb-4f63750c9518")  
  
    > [!NOTE]
    >  在根级别，如 ExecuteReader、 ExecuteScalar 和 ExecuteNonQuery 的标准操作均可用。 有关这些操作的详细信息，请参阅[支持 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)。 有关如何执行这些操作使用的说明[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，请参阅[ExecuteReader、 ExecuteScalar 或在 SQL 中使用 BizTalk Server ExecuteNonQuery 操作](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md)。  
  
4.  展开**基于架构的视图**节点以查看在基础数据库中定义的架构。 每个架构进行进一步分类根据 PL SQL Api、 过程、 函数、 表和它包含的视图。  
  
    > [!TIP]
    >  你可以直接转到"即时"类别节点或子类别节点在树中，通过键入项目的名称上时将焦点的树视图中**选择类别**框。 例如，若要跳转到**SCOTT**架构，关注**基于架构的视图**节点，并键入`SCOTT`。  
  
5.  展开**PL SQL Api**节点以查看为特定架构的 Oracle 数据库中定义的包的列表。 单击以查看的函数和过程在包内定义的包名称**可用类别和操作**框。  
  
     ![浏览 Oracle 数据库中的包](../../adapters-and-accelerators/adapter-oracle-ebs/media/582a9bd7-beed-4b36-b465-f5c4ceb6e740.gif "582a9bd7-beed-4b36-b465-f5c4ceb6e740")  
  
6.  单击**过程**节点以查看中的步骤列表**可用类别和操作**框。  
  
     ![浏览 Oracle 数据库中的过程](../../adapters-and-accelerators/adapter-oracle-ebs/media/7213154e-6a26-4fc3-b4ec-1658779f77d3.gif "7213154e-6a26-4fc3-b4ec-1658779f77d3")  
  
7.  单击**函数**节点以查看中的函数列表**可用类别和操作**框。  
  
     ![浏览 Oracle 数据库中的 funcitons](../../adapters-and-accelerators/adapter-oracle-ebs/media/5df9b42c-9d8b-4c81-a0ae-ba5336445837.gif "5df9b42c-9d8b-4c81-a0ae-ba5336445837")  
  
8.  展开**表**节点以查看为特定架构的表的列表。 单击某个表名称以查看上的表中支持的操作**可用类别和操作**框。  
  
     ![浏览 Oracle 数据库中表](../../adapters-and-accelerators/adapter-oracle-ebs/media/94dd4642-1178-4d88-986b-f0ad409c414c.gif "94dd4642-1178-4d88-986b-f0ad409c414c")  
  
    > [!NOTE]
    >  如果表包含 BLOB 类型的列，CLOB、 NCLOB、 BFILE 适配器还公开从这类列读取数据的特定操作。 此类操作的名称是否 Read_\<LOBColName >。 例如，如果表中包含列，照片，类型 BLOB，则适配器将公开**Read_PHOTO**操作。 如果表具有多个列类型 BLOB，CLOB、 NCLOB、 BFILE 适配器将公开任意多个数 Read_\<LOBColName > 操作。  
    >   
    >  同样，如果表包含 BLOB 类型的列，CLOB、 或 NCLOB 适配器还公开特定操作来更新到此类列的数据。 此类操作的名称是否 Update_\<LOBColName >。 例如，如果表中包含列，照片，类型 BLOB，则适配器将公开**Update_PHOTO**操作。 如果表具有多个列类型 BLOB，CLOB、 和 NCLOB 适配器将公开任意多个数 Update_\<LOBColName > 操作。 请注意，对类型 BFILE 的列不支持更新操作。  
  
9. 展开**视图**节点以查看为特定架构的视图的列表。 单击以查看中的视图支持的操作的视图名称**可用类别和操作**框。  
  
     ![Oracle 数据库中的视图浏览](../../adapters-and-accelerators/adapter-oracle-ebs/media/e1893e48-065c-4642-b076-192758d103db.gif "e1893e48-065c-4642-b076-192758d103db")  
  
    > [!NOTE]
    >  如果视图包含类型 BLOB 的列，CLOB、 NCLOB、 BFILE 适配器还公开从这类列读取数据的特定操作。 此类操作的名称是否 Read_\<LOBColName >。 例如，如果视图有一列，类型 BLOB 的规则，该适配器将公开**Read_RULE**操作。 如果某个视图具有多个列类型 BLOB、 CLOB、 NCLOB、 BFILE 适配器将公开任意多个系列 Read_\<LOBColName > 操作。 请注意该 Update_\<LOBColName > 视图不支持操作。  
  
## <a name="browsing-for-inbound-operations"></a>为入站操作浏览  
 执行以下步骤以浏览基于架构的视图下的入站的操作。  
  
#### <a name="to-browse-metadata-for-inbound-operations-under-the-schema-based-view"></a>若要浏览基于架构的视图下的入站操作的元数据  
  
1.  连接到 Oracle E-business Suite 使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 请参阅[连接到 Visual Studio 中 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)有关的说明。  
  
2.  从**选择协定类型**列出，请为入站的操作选择**服务 （入站操作）**。  
  
3.  **选择类别**框中列出的在其下的 Oracle E-business Suite 项目进行分类的不同视图。  
  
     下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 选择根节点 （/），并且中列出了可用的根节点下的常规类别节点**可用类别和操作**框。  
  
     ![入站操作在根级别](../../adapters-and-accelerators/adapter-oracle-ebs/media/9f9f95f3-c6cc-415c-b534-d5f1ad1963d5.gif "9f9f95f3-c6cc-415c-b534-d5f1ad1963d5")  
  
     入站的操作，**通知**，在根级别也是可用。  
  
4.  展开**基于架构的视图**节点以查看在基础数据库中定义的架构。 每个架构进行进一步分类根据 PL SQL Api、 过程、 函数、 表和它包含的视图。  
  
    > [!TIP]
    >  你可以直接转到"即时"类别节点或子类别节点在树中，通过键入项目的名称上时将焦点的树视图中**选择类别**框。 例如，若要跳转到**SCOTT**架构，关注**基于架构的视图**节点，并键入`SCOTT`。  
  
5.  展开**PL SQL Api**节点以查看为特定架构的 Oracle 数据库中定义的包的列表。 单击以查看的函数和过程在包内定义的包名称**可用类别和操作**框。 可以使用每个列出的函数和过程来轮询 Oracle 数据库。  
  
     ![浏览进行轮询的 Oracle 数据库中的包](../../adapters-and-accelerators/adapter-oracle-ebs/media/ab45e4a3-1425-4b23-afc2-8aecef546802.gif "ab45e4a3-1425-4b23-afc2-8aecef546802")  
  
6.  单击**过程**节点以查看中的步骤列表**可用类别和操作**框。 每个列出的过程可用于轮询 Oracle 数据库。  
  
     ![浏览进行轮询的 Oracle 数据库中的过程](../../adapters-and-accelerators/adapter-oracle-ebs/media/04538693-5abf-4162-82e9-4107b4088b56.gif "04538693-5abf-4162-82e9-4107b4088b56")  
  
7.  单击**函数**节点以查看中的函数列表**可用类别和操作**框。 每个列出的函数可用来轮询 Oracle 数据库。  
  
     ![浏览进行轮询的 Oracle 数据库中的函数](../../adapters-and-accelerators/adapter-oracle-ebs/media/b3f4ea5b-d03f-4cb5-82b4-8fbf0a8af24b.gif "b3f4ea5b-d03f-4cb5-82b4-8fbf0a8af24b")  
  
8.  展开**表**节点以查看为特定架构的表的列表。 单击表名以查看**轮询**入站操作上的表中支持**可用类别和操作**框。  
  
     ![浏览进行轮询的 Oracle 数据库中表](../../adapters-and-accelerators/adapter-oracle-ebs/media/58e9315d-3194-4a01-a505-bd1514e9d7e3.gif "58e9315d-3194-4a01-a505-bd1514e9d7e3")  
  
9. 展开**视图**节点以查看为特定架构的视图的列表。 单击某个视图名称以查看**轮询**入站操作中的视图支持**可用类别和操作**框。  
  
     ![浏览进行轮询的 Oracle 数据库中的视图](../../adapters-and-accelerators/adapter-oracle-ebs/media/f1282f17-efbe-43e6-90fa-5676e04051e8.gif "f1282f17-efbe-43e6-90fa-5676e04051e8")  
  
## <a name="see-also"></a>另请参阅  
 [浏览、 搜索和用于 Oracle E-business Suite 操作获取元数据](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)