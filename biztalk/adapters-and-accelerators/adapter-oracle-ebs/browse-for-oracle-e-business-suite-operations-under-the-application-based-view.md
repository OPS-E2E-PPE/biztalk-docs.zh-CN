---
title: "浏览基于应用程序的视图下的 Oracle E-business Suite 操作 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fb207869-1a19-4e19-ba47-c78d2a29b36d
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d06cf551d033614cb75456845e059c6ec4ec8fa8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="browse-for-oracle-e-business-suite-operations-under-the-application-based-view"></a>浏览基于应用程序的视图下的 Oracle E-business Suite 操作
你可以使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]若要浏览的出站和入站操作，可以对 Oracle E-business Suite 执行使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 本主题提供有关如何浏览基于应用程序的视图下的出站和入站操作的信息。  
  
> [!NOTE]
>  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]和[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]当您浏览和搜索操作，因此相同的主题中所述两个组件时所显示实质上是相同的接口。  
  
## <a name="prerequisites"></a>先决条件  
 你可以浏览元数据的目标操作之前，你必须连接到 Oracle E-business Suite。 有关如何连接到 Oracle 数据库使用时[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，请参阅[连接到 Visual Studio 中 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)。  
  
## <a name="browsing-for-outbound-operations"></a>为出站操作浏览  
 执行以下步骤以浏览基于应用程序的视图下的出站操作。  
  
#### <a name="to-browse-metadata-for-outbound-operations-under-the-application-based-view"></a>若要浏览应用程序基于视图下的出站操作的元数据  
  
1.  连接到 Oracle E-business Suite 使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 请参阅[连接到 Visual Studio 中 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)有关的说明。  
  
2.  从**选择协定类型**列表中，选择**客户端 （出站操作）**。  
  
3.  **选择类别**框中列出的在其下的 Oracle E-business Suite 项目进行分类的不同视图。  
  
     下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 选择根节点 （/），并且中列出了可用的根节点下的常规类别节点**可用类别和操作**框。  
  
     ![操作和在根级别的类别](../../adapters-and-accelerators/adapter-oracle-ebs/media/559a6652-2d9d-4ecd-a1bb-4f63750c9518.gif "559a6652-2d9d-4ecd-a1bb-4f63750c9518")  
  
    > [!NOTE]
    >  在根级别，如 ExecuteReader、 ExecuteScalar 和 ExecuteNonQuery 的标准操作均可用。 有关这些操作的详细信息，请参阅[支持 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)。 有关如何执行这些操作使用的说明[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，请参阅[ExecuteReader、 ExecuteScalar 或在 SQL 中使用 BizTalk Server ExecuteNonQuery 操作](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md)。  
  
4.  展开**基于应用程序的视图**节点连接到的服务器上查看所有 Oracle E-business suite 应用程序可用。 展开要查看界面表、 界面视图、 并发程序的类别的应用程序和请求设置为该应用程序可用。  
  
    > [!TIP]
    >  你可以直接转到"即时"类别节点或子类别节点在树中，通过键入中项目的名称上时将焦点的树视图中**选择类别**框。 例如，若要跳转到**警报**节点，关注**基于应用程序的视图**节点，并键入`Alert`。  
  
5.  展开**接口表**节点以查看表的 Oracle 应用程序中的接口。 单击以查看可用的操作列表中的表接口表**可用类别和操作**框。  
  
     ![浏览接口 Oracle （&#45;） 中的表Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/media/fcfbe41c-14e0-43b5-aada-c4c686aecff4.gif "fcfbe41c-14e0-43b5-aada-c4c686aecff4")  
  
    > [!NOTE]
    >  如果接口表包含 BLOB 类型的列，CLOB、 NCLOB、 BFILE 适配器还公开从这类列读取数据的特定操作。 此类操作的名称是否 Read_\<LOBColName >。 例如，如果接口表有一列，FILE_DATA 的类型 BLOB，该适配器将公开**Read_FILE_DATA**操作。 如果某个接口表具有多个列类型 BLOB，CLOB、 NCLOB、 BFILE 适配器将公开任意多个数 Read_\<LOBColName > 操作。  
    >   
    >  同样，如果接口表包含 BLOB 类型的列，CLOB、 或 NCLOB 适配器还公开特定操作来更新到此类列的数据。 此类操作的名称是否 Update_\<LOBColName >。 例如，如果接口表有一列，FILE_DATA 的类型 BLOB，该适配器将公开**Update_FILE_DATA**操作。 如果某个接口表具有多个列类型 BLOB，CLOB、 和 NCLOB 适配器将公开任意多个数 Update_\<LOBColName > 操作。 请注意，对类型 BFILE 的列不支持更新操作。  
  
6.  展开**界面视图**节点可查看的 Oracle 应用程序的接口视图。 单击接口视图以查看可用的操作列表中的视图为**可用类别和操作**框。  
  
     ![浏览 Oracle （&#45;） 中的接口视图Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/media/f1dc14cc-ad77-47ed-b0b0-b5fc78ed545b.gif "f1dc14cc-ad77-47ed-b0b0-b5fc78ed545b")  
  
    > [!NOTE]
    >  如果接口视图包含类型 BLOB 的列，CLOB、 NCLOB、 BFILE 适配器还公开从这类列读取数据的特定操作。 此类操作的名称是否 Read_\<LOBColName >。 例如，如果接口视图有一列，FILE_CONTENT 的类型 BLOB，该适配器将公开**Read_FILE_CONTENT**操作。 如果接口视图具有多个列类型 BLOB，CLOB、 NCLOB、 BFILE 适配器将公开任意多个系列 Read_\<LOBColName > 操作。 请注意该 Update_\<LOBColName > 视图不支持操作。  
  
7.  单击**并发程序**节点以查看有关中的应用程序的并发程序**可用类别和操作**框。  
  
     ![浏览 Oracle 应用程序的并发程序](../../adapters-and-accelerators/adapter-oracle-ebs/media/71173055-4250-4406-838b-c5e9d6bf9e8c.gif "71173055-4250-4406-838b-c5e9d6bf9e8c")  
  
     此图显示特定于 Oracle 应用程序的并发程序和 Oracle 的所有应用程序的标准并发程序。  
  
    > [!IMPORTANT]
    >  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] (或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]) 显示的并发程序的友好名称。 但是，并发程序的元数据具有并发程序的实际名称。 例如，应收帐款应用程序包含"客户接口"并发程序。 但是，元数据作为 RACUST，是并发的程序的实际名称具有并发程序的名称。  
  
8.  单击**请求设置**节点以查看请求设置中的应用程序**可用类别和操作**框。  
  
     ![浏览 Oracle 应用程序的请求集](../../adapters-and-accelerators/adapter-oracle-ebs/media/0934f6f5-0d7a-4dad-a550-e7a4f524551b.gif "0934f6f5-0d7a-4dad-a550-e7a4f524551b")  
  
    > [!IMPORTANT]
    >  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] (或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]) 显示的请求集的友好名称。 但是，请求集的元数据已请求集的实际名称。 例如，应用程序 DBA 应用程序包含一"DownloadPatches"请求组。 但是，元数据已请求集名称作为 FNDRSSUB1623，这是请求集的实际名称。  
  
## <a name="browsing-for-inbound-operations"></a>为入站操作浏览  
 执行以下步骤以浏览基于应用程序的视图下的入站的操作。  
  
#### <a name="to-browse-metadata-for-inbound-operations-under-the-application-based-view"></a>若要浏览应用程序基于视图下的入站操作的元数据  
  
1.  连接到 Oracle E-business Suite 使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 请参阅[连接到 Visual Studio 中 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)有关的说明。  
  
2.  从**选择协定类型**列出，请为入站的操作选择**服务 （入站操作）**。  
  
3.  **选择类别**框中列出的在其下的 Oracle E-business Suite 项目进行分类的不同视图。  
  
     下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 选择根节点 （/），并且中列出了可用的根节点下的常规类别节点**可用类别和操作**框。  
  
     ![入站操作在根级别](../../adapters-and-accelerators/adapter-oracle-ebs/media/9f9f95f3-c6cc-415c-b534-d5f1ad1963d5.gif "9f9f95f3-c6cc-415c-b534-d5f1ad1963d5")  
  
     入站的操作，**通知**，在根级别也是可用。  
  
4.  展开**基于应用程序的视图**节点连接到的服务器上查看所有 Oracle E-business suite 应用程序可用。 展开要查看界面表和接口视图类别的应用程序。  
  
    > [!TIP]
    >  你可以直接转到"即时"类别节点或子类别节点在树中，通过键入中项目的名称上时将焦点的树视图中**选择类别**框。 例如，若要跳转到**警报**节点，关注**基于应用程序的视图**节点，并键入`Alert`。  
  
5.  展开的 Oracle 应用程序，以查看接口表和接口视图可用于该应用程序的类别。 展开**接口表**和**界面视图**节点以查看接口表和 Oracle 应用程序的界面视图。 单击以查看表的入站的操作或查看中的接口表或接口视图**可用类别和操作**框。  
  
     在下图中，选择接口视图中**选择类别**框以及支持在视图上的入站的操作被列入**可用类别和操作**框。  
  
     ![入站界面视图上的操作](../../adapters-and-accelerators/adapter-oracle-ebs/media/937f46f2-d142-413f-8744-2180c7116fd4.gif "937f46f2-d142-413f-8744-2180c7116fd4")  
  
    > [!NOTE]
    >  [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不外围并发节目，请求的入站操作集。  
  
## <a name="see-also"></a>另请参阅  
 [浏览、 搜索和用于 Oracle E-business Suite 操作获取元数据](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)