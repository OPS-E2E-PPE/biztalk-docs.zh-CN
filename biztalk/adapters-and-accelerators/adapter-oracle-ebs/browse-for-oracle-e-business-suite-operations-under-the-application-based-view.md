---
title: 用于 Oracle E-business Suite 操作基于应用程序的视图下浏览 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb207869-1a19-4e19-ba47-c78d2a29b36d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51abb0e1351d63baa86ccc5d2443064e557d5cba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375783"
---
# <a name="browse-for-oracle-e-business-suite-operations-under-the-application-based-view"></a>用于 Oracle E-business Suite 操作基于应用程序的视图下浏览
可以使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]浏览到可执行 Oracle E-business Suite 的出站和入站操作使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 本主题提供有关如何为出站和入站操作基于应用程序的视图下浏览信息。  
  
> [!NOTE]
>  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]和[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]时浏览和搜索操作，因此同样的主题中介绍了这两个组件显示实质上是相同的接口。  
  
## <a name="prerequisites"></a>先决条件  
 您可以浏览元数据的目标操作之前，必须连接到 Oracle E-business Suite。 有关如何连接到 Oracle 数据库的信息时则使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，请参阅[连接到在 Visual Studio 中的 Oracle 电子商务套件](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)。  
  
## <a name="browsing-for-outbound-operations"></a>浏览为出站操作  
 执行以下步骤以浏览基于应用程序的视图下的出站操作。  
  
#### <a name="to-browse-metadata-for-outbound-operations-under-the-application-based-view"></a>若要浏览基于应用程序的视图下的出站操作的元数据  
  
1. 连接到 Oracle E-business Suite 使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 请参阅[连接到在 Visual Studio 中的 Oracle 电子商务套件](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)有关的说明。  
  
2. 从**选择协定类型**列表中，选择**客户端 （出站操作）**。  
  
3. **选择一个类别**框中列出的在其下的 Oracle E-business Suite 项目进行分类的不同视图。  
  
    下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 选择根节点 （/），并且可用的根节点下的常规类别节点中列出**可用类别和操作**框。  
  
    ![操作和类别的根级别](../../adapters-and-accelerators/adapter-oracle-ebs/media/559a6652-2d9d-4ecd-a1bb-4f63750c9518.gif "559a6652-2d9d-4ecd-a1bb-4f63750c9518")  
  
   > [!NOTE]
   >  ExecuteReader、 ExecuteScalar ExecuteNonQuery 等标准操作在根级别均可用。 有关这些操作的详细信息，请参阅[支持 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)。 有关如何执行这些操作使用的说明[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，请参阅[ExecuteReader、 ExecuteScalar 或 ExecuteNonQuery 操作中使用 BizTalk Server 的 SQL](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md)。  
  
4. 展开**基于应用程序的视图**节点以查看所有 Oracle E-business suite 可用的应用程序连接到的服务器上。 展开以查看接口表、 界面视图、 并发程序的类别的应用程序，并请求设置可用于该应用程序。  
  
   > [!TIP]
   >  您可以直接转到"即时"类别节点或子类别节点在树中，通过键入中项目的名称的树视图中聚焦时**选择一个类别**框。 例如，若要跳转到**警报**节点，重点介绍**基于应用程序的视图**节点，并键入`Alert`。  
  
5. 展开**接口表**节点以查看 Oracle 应用程序的接口表。 单击一个接口表以查看可用于在表的操作列表**可用类别和操作**框。  
  
    ![浏览 Oracle 电子中的接口表&#45;Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/media/fcfbe41c-14e0-43b5-aada-c4c686aecff4.gif "fcfbe41c-14e0-43b5-aada-c4c686aecff4")  
  
   > [!NOTE]
   >  如果接口表包含 BLOB 类型的列，CLOB、 NCLOB、 或 BFILE 适配器还公开从这样的列读取数据的特定操作。 此类操作的名称是 Read_\<LOBColName\>。 例如，如果接口表具有列，FILE_DATA 的 BLOB，类型适配器公开**Read_FILE_DATA**操作。 如果某个接口表具有多个 BLOB 类型的列，CLOB 和 NCLOB、 BFILE 适配器将公开任意多个系列 Read_\<LOBColName\>操作。  
   >   
   >  同样，如果接口表包含 BLOB 类型的列，CLOB、 或 NCLOB 适配器还公开了特定操作来更新到此类列的数据。 此类操作的名称是 Update_\<LOBColName\>。 例如，如果接口表具有列，FILE_DATA 的 BLOB，类型适配器公开**Update_FILE_DATA**操作。 如果某个接口表具有多个 BLOB 类型的列，CLOB、 和 NCLOB 适配器将公开任意多个系列 Update_\<LOBColName\>操作。 请注意类型 BFILE 的列上不支持更新操作。  
  
6. 展开**界面视图**节点以查看 Oracle 应用程序的接口视图。 单击以查看可用于中的视图的操作列表的接口视图**可用类别和操作**框。  
  
    ![浏览 Oracle E 中的界面视图&#45;Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/media/f1dc14cc-ad77-47ed-b0b0-b5fc78ed545b.gif "f1dc14cc-ad77-47ed-b0b0-b5fc78ed545b")  
  
   > [!NOTE]
   >  如果接口视图包含 BLOB 类型的列，CLOB、 NCLOB、 或 BFILE 适配器还公开从这样的列读取数据的特定操作。 此类操作的名称是 Read_\<LOBColName\>。 例如，如果接口视图具有列，FILE_CONTENT 的 BLOB，类型适配器公开**Read_FILE_CONTENT**操作。 CLOB、 NCLOB、 或 BFILE 适配器的接口视图有多个 BLOB 类型的列，如果将公开任意多个系列 Read_\<LOBColName\>操作。 请注意该 Update_\<LOBColName\>视图上不支持操作。  
  
7. 单击**并发程序**节点以查看中的应用程序的并发程序**可用类别和操作**框。  
  
    ![浏览 Oracle 应用程序的并发程序](../../adapters-and-accelerators/adapter-oracle-ebs/media/71173055-4250-4406-838b-c5e9d6bf9e8c.gif "71173055-4250-4406-838b-c5e9d6bf9e8c")  
  
    此图显示了特定于 Oracle 应用程序的并发程序和标准的并发程序的所有 Oracle 应用程序。  
  
   > [!IMPORTANT]
   >  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] (或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]) 显示的并发程序的友好名称。 但是，并发程序的元数据具有并发程序的实际名称。 例如，应收帐款应用程序包含"客户接口"并发程序。 但是，元数据作为 RACUST，是并发程序的实际名称具有并发程序名称。  
  
8. 单击**请求设置**节点，可以看到请求设置中为应用程序**可用类别和操作**框。  
  
    ![浏览 Oracle 应用程序的请求集](../../adapters-and-accelerators/adapter-oracle-ebs/media/0934f6f5-0d7a-4dad-a550-e7a4f524551b.gif "0934f6f5-0d7a-4dad-a550-e7a4f524551b")  
  
   > [!IMPORTANT]
   >  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] (或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]) 显示的请求集的友好名称。 但是，请求集的元数据已请求集的实际名称。 例如，应用程序 DBA 应用程序包含"DownloadPatches"请求集。 但是，元数据的请求集名称作为具有 FNDRSSUB1623，这是请求集的实际名称。  
  
## <a name="browsing-for-inbound-operations"></a>浏览的入站操作  
 执行以下步骤以浏览基于应用程序的视图下的入站的操作。  
  
#### <a name="to-browse-metadata-for-inbound-operations-under-the-application-based-view"></a>若要浏览基于应用程序的视图下的入站操作的元数据  
  
1. 连接到 Oracle E-business Suite 使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 请参阅[连接到在 Visual Studio 中的 Oracle 电子商务套件](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)有关的说明。  
  
2. 从**选择协定类型**列表中，为入站的操作选择**服务 （入站操作）**。  
  
3. **选择一个类别**框中列出的在其下的 Oracle E-business Suite 项目进行分类的不同视图。  
  
    下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 选择根节点 （/），并且可用的根节点下的常规类别节点中列出**可用类别和操作**框。  
  
    ![在根级别的操作的入站](../../adapters-and-accelerators/adapter-oracle-ebs/media/9f9f95f3-c6cc-415c-b534-d5f1ad1963d5.gif "9f9f95f3-c6cc-415c-b534-d5f1ad1963d5")  
  
    入站的操作，**通知**，在根级别也是可用。  
  
4. 展开**基于应用程序的视图**节点以查看所有 Oracle E-business suite 可用的应用程序连接到的服务器上。 展开要查看的接口表和界面视图类别的应用程序。  
  
   > [!TIP]
   >  您可以直接转到"即时"类别节点或子类别节点在树中，通过键入中项目的名称的树视图中聚焦时**选择一个类别**框。 例如，若要跳转到**警报**节点，重点介绍**基于应用程序的视图**节点，并键入`Alert`。  
  
5. 展开 Oracle 应用程序若要查看界面表和界面视图可用于该应用程序的类别。 展开**接口表**并**界面视图**节点以查看界面表和 Oracle 应用程序的界面视图。 单击以查看入站的操作适用的表或视图中的接口表或界面视图**可用类别和操作**框。  
  
    在下图中，在中选择的接口视图**选择一个类别**框和入站的操作支持在视图上被列入**可用类别和操作**框。  
  
    ![界面视图上的操作的入站](../../adapters-and-accelerators/adapter-oracle-ebs/media/937f46f2-d142-413f-8744-2180c7116fd4.gif "937f46f2-d142-413f-8744-2180c7116fd4")  
  
   > [!NOTE]
   >  [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不会出现并发程序和请求的入站操作集。  
  
## <a name="see-also"></a>请参阅  
 [浏览、 搜索和获取 Oracle E-business Suite 操作的元数据](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)