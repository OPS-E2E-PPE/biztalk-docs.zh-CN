---
title: 用于 Oracle E-business Suite 操作基于项目的视图下浏览 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 962ac1cc-826c-46d6-848a-4cd371804596
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d5af2639b846bdde1e7f892a74e12eeae392363
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375767"
---
# <a name="browse-for-oracle-e-business-suite-operations-under-the-artifact-based-view"></a>用于 Oracle E-business Suite 操作基于项目的视图下浏览
可以使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]浏览到可执行 Oracle E-business Suite 的出站和入站操作使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 本主题提供有关如何为出站和入站操作基于项目的视图下浏览信息。  
  
> [!NOTE]
>  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]和[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]时浏览和搜索操作，因此同样的主题中介绍了这两个组件显示实质上是相同的接口。  
  
## <a name="prerequisites"></a>先决条件  
 您可以浏览元数据的目标操作之前，必须连接到 Oracle E-business Suite。 有关如何连接到 Oracle 数据库的信息时则使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，请参阅[连接到在 Visual Studio 中的 Oracle 电子商务套件](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)。  
  
## <a name="browsing-for-outbound-operations"></a>浏览为出站操作  
 执行以下步骤以浏览基于项目的视图下的出站操作。  
  
#### <a name="to-browse-metadata-for-outbound-operations-under-the-artifact-based-view"></a>若要浏览基于项目的视图下的出站操作的元数据  
  
1. 连接到 Oracle E-business Suite 使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 请参阅[连接到在 Visual Studio 中的 Oracle 电子商务套件](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)有关的说明。  
  
2. 从**选择协定类型**列表中，为出站操作选择**客户端 （出站操作）**。  
  
3. **选择一个类别**框中列出的在其下的 Oracle E-business Suite 项目进行分类的不同视图。  
  
    下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 选择根节点 （/），并且可用的根节点下的常规类别节点中列出**可用类别和操作**框。  
  
    ![操作和类别的根级别](../../adapters-and-accelerators/adapter-oracle-ebs/media/559a6652-2d9d-4ecd-a1bb-4f63750c9518.gif "559a6652-2d9d-4ecd-a1bb-4f63750c9518")  
  
   > [!NOTE]
   >  ExecuteReader、 ExecuteScalar ExecuteNonQuery 等标准操作在根级别均可用。 有关这些操作的详细信息，请参阅[支持 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)。 有关如何执行这些操作使用的说明[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，请参阅[ExecuteReader、 ExecuteScalar 或 ExecuteNonQuery 操作中使用 BizTalk Server 的 SQL](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md)。  
  
4. 展开**基于项目的视图**节点，可以看到，用于 Oracle E-business Suite 和基础数据库项目的类别。 每个类别是进一步分类基于其所属 （适用于 Oracle 电子商务套件项目，例如接口表、 界面视图、 并发程序和请求集） 的应用程序或其所属 （用于 Oracle 数据库等项目的架构PL-SQL Api、 过程、 函数、 表和视图)。  
  
   > [!TIP]
   >  您可以直接转到"即时"类别节点或子类别节点在树中，键入项目的名称的树视图中聚焦时**选择一个类别**框。 例如，若要跳转到**过程**节点，重点介绍**基于项目的视图**节点，并键入`Procedures`。  
  
5. 展开**接口表**节点以查看所有 Oracle E-business Suite 应用程序。 展开 Oracle E-business suite 应用程序以列出属于该应用程序的所有接口表。 单击要查看适用于中的表操作的接口表名称**可用类别和操作**框。  
  
   > [!NOTE]
   >  如果接口表包含 BLOB 类型的列，CLOB、 NCLOB、 或 BFILE 适配器还公开从这样的列读取数据的特定操作。 此类操作的名称是 Read_\<LOBColName\>。 例如，如果接口表具有列，FILE_DATA 的 BLOB，类型适配器公开**Read_FILE_DATA**操作。 如果某个接口表具有多个 BLOB 类型的列，CLOB 和 NCLOB、 BFILE 适配器将公开任意多个系列 Read_\<LOBColName\>操作。  
   >   
   >  同样，如果接口表包含 BLOB 类型的列，CLOB、 或 NCLOB 适配器还公开了特定操作来更新到此类列的数据。 此类操作的名称是 Update_\<LOBColName\>。 例如，如果接口表具有列，FILE_DATA 的 BLOB，类型适配器公开**Update_FILE_DATA**操作。 如果某个接口表具有多个 BLOB 类型的列，CLOB、 和 NCLOB 适配器将公开任意多个系列 Update_\<LOBColName\>操作。 请注意类型 BFILE 的列上不支持更新操作。  
  
6. 展开**界面视图**节点以查看所有 Oracle E-business Suite 应用程序。 展开 Oracle E-business suite 应用程序若要列出属于该应用程序的所有接口视图。 单击要查看适用于视图中操作的接口视图名称**可用类别和操作**框。  
  
   > [!NOTE]
   >  如果接口视图包含 BLOB 类型的列，CLOB、 NCLOB、 或 BFILE 适配器还公开从这样的列读取数据的特定操作。 此类操作的名称是 Read_\<LOBColName\>。 例如，如果接口视图具有列，FILE_CONTENT 的 BLOB，类型适配器公开**Read_FILE_CONTENT**操作。 CLOB、 NCLOB、 或 BFILE 适配器的接口视图有多个 BLOB 类型的列，如果将公开任意多个系列 Read_\<LOBColName\>操作。 请注意该 Update_\<LOBColName\>视图上不支持操作。  
  
7. 展开**并发程序**节点以查看所有 Oracle E-business Suite 应用程序。 单击 Oracle E-business suite 应用程序属于该应用程序中的所有并发程序列出**可用类别和操作**框。  
  
   > [!IMPORTANT]
   >  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] (或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]) 显示的并发程序的友好名称。 但是，并发程序的元数据具有并发程序的实际名称。 例如，应收帐款应用程序包含"客户接口"并发程序。 但是，元数据作为 RACUST，是并发程序的实际名称具有并发程序名称。  
  
8. 展开**请求集**节点以查看所有 Oracle E-business Suite 应用程序。 单击 Oracle E-business suite 应用程序若要列出属于该应用程序中的所有请求集**可用类别和操作**框。  
  
   > [!IMPORTANT]
   >  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] (或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]) 显示的请求集的友好名称。 但是，请求集的元数据已请求集的实际名称。 例如，应用程序 DBA 应用程序包含"DownloadPatches"请求集。 但是，元数据的请求集名称作为具有 FNDRSSUB1623，这是请求集的实际名称。  
  
9. 展开**PL-SQL Api**节点以查看类别 （登录与其） 的当前用户架构和基础的 Oracle 数据库中定义的所有其他架构的节点。 展开**当前架构 (\<架构名称\>)** 节点以查看为该架构定义的所有包。 单击要查看的函数和过程中的包中的包名称**可用类别和操作**框。  
  
     ![浏览 Oracle 数据库中的软件包](../../adapters-and-accelerators/adapter-oracle-ebs/media/7a9dc061-db0b-4a8e-bfc6-3a003ad687d8.gif "7a9dc061-db0b-4a8e-bfc6-3a003ad687d8")  
  
     同样，展开**所有架构**节点以查看 Oracle 数据库中定义的所有架构的列表。 展开 schema 节点以查看为该架构定义的包的列表。 单击要查看的函数和过程中的包中的包名称**可用类别和操作**框。  
  
     ![浏览 Oracle 数据库中的所有架构的软件包](../../adapters-and-accelerators/adapter-oracle-ebs/media/09a4841b-b88f-490d-a49a-94e392b5493c.gif "09a4841b-b88f-490d-a49a-94e392b5493c")  
  
10. 展开**过程**节点以查看类别 （登录与其） 的当前用户架构和基础的 Oracle 数据库中定义的所有其他架构的节点。 单击**当前架构 (\<架构名称\>)** 节点，查看为该架构中定义的所有过程**可用类别和操作**框。  
  
     ![浏览 Oracle 数据库中的架构的过程](../../adapters-and-accelerators/adapter-oracle-ebs/media/6d78563a-53f7-45cc-8652-f40d4703bdf4.gif "6d78563a-53f7-45cc-8652-f40d4703bdf4")  
  
     同样，展开**所有架构**节点以查看 Oracle 数据库中定义的所有架构的列表。 单击架构节点以查看为该架构中定义的过程的列表**可用类别和操作**框。  
  
     ![浏览 Oracle 数据库中的架构的过程](../../adapters-and-accelerators/adapter-oracle-ebs/media/a514d199-d6c1-44a0-bf6b-28ddf702081a.gif "a514d199-d6c1-44a0-bf6b-28ddf702081a")  
  
11. 展开**函数**节点以查看类别 （登录与其） 的当前用户架构和基础的 Oracle 数据库中定义的所有其他架构的节点。 单击**当前架构 (\<架构名称\>)** 节点，查看为该架构中定义的所有函数**可用类别和操作**框。  
  
     ![浏览 Oracle 数据库中的架构的函数](../../adapters-and-accelerators/adapter-oracle-ebs/media/22c1cabf-9754-4ecd-be37-dbeeb7a6a8fd.gif "22c1cabf-9754-4ecd-be37-dbeeb7a6a8fd")  
  
     同样，展开**所有架构**节点以查看 Oracle 数据库中定义的所有架构的列表。 单击架构节点以查看为该架构中定义的函数的列表**可用类别和操作**框。  
  
     ![浏览 Oracle 数据库中的所有架构的函数](../../adapters-and-accelerators/adapter-oracle-ebs/media/b4d29036-3d37-4a50-82c2-3532adbe2875.gif "b4d29036-3d37-4a50-82c2-3532adbe2875")  
  
12. 展开**表**节点以查看类别 （登录与其） 的当前用户架构和基础的 Oracle 数据库中定义的所有其他架构的节点。 展开**当前架构 (\<架构名称\>)** 节点可以查看为该架构定义的所有表。 单击表名以查看在此表中支持的操作**可用类别和操作**框。  
  
     ![浏览 Oracle 数据库中的表架构](../../adapters-and-accelerators/adapter-oracle-ebs/media/6ba7420f-9893-4b3e-91cb-10f29d725ad3.gif "6ba7420f-9893-4b3e-91cb-10f29d725ad3")  
  
     同样，展开**所有架构**节点以查看 Oracle 数据库中定义的所有架构的列表。 展开 schema 节点以查看为该架构定义的表的列表。 单击表名以查看在此表中支持的操作**可用类别和操作**框。  
  
     ![浏览用于所有架构的 Oracle 数据库表](../../adapters-and-accelerators/adapter-oracle-ebs/media/d7c52ab4-ba27-404a-9db6-32b2a635ad2f.gif "d7c52ab4-ba27-404a-9db6-32b2a635ad2f")  
  
    > [!NOTE]
    >  如果表中包含的 BLOB 类型列、 CLOB、 NCLOB、 或 BFILE 适配器还公开从这样的列读取数据的特定操作。 此类操作的名称是 Read_\<LOBColName\>。 例如，如果表具有的列的类型 BLOB，照片适配器公开**Read_PHOTO**操作。 如果表具有多个 BLOB 类型的列，CLOB 和 NCLOB、 BFILE 适配器将公开任意多个系列 Read_\<LOBColName\>操作。  
    >   
    >  同样，如果表中包含 BLOB 类型的列，CLOB、 或 NCLOB 适配器还公开了特定操作来更新到此类列的数据。 此类操作的名称是 Update_\<LOBColName\>。 例如，如果表具有的列的类型 BLOB，照片适配器公开**Update_PHOTO**操作。 如果表具有多个 BLOB 类型的列，CLOB、 和 NCLOB 适配器将公开任意多个系列 Update_\<LOBColName\>操作。 请注意类型 BFILE 的列上不支持更新操作。  
  
13. 展开**视图**节点以查看类别 （登录与其） 的当前用户架构和基础的 Oracle 数据库中定义的所有其他架构的节点。 展开**当前架构 (\<架构名称\>)** 节点以查看为此定义的所有视图。 单击以查看该视图中支持的操作的视图名称**可用类别和操作**框。  
  
     ![浏览 Oracle 数据库中的当前架构的视图](../../adapters-and-accelerators/adapter-oracle-ebs/media/2a38cfed-007d-431a-af60-c9c8be5369ab.gif "2a38cfed-007d-431a-af60-c9c8be5369ab")  
  
     同样，展开**所有架构**节点以查看 Oracle 数据库中定义的所有架构的列表。 展开 schema 节点以查看为该架构定义的视图的列表。 单击以查看该视图中支持的操作的视图名称**可用类别和操作**框。  
  
     ![浏览 Oracle 数据库中的所有架构的视图](../../adapters-and-accelerators/adapter-oracle-ebs/media/67ca336c-62ac-4374-87da-07cf331ea4ad.gif "67ca336c-62ac-4374-87da-07cf331ea4ad")  
  
    > [!NOTE]
    >  如果视图包含 BLOB 类型的列，CLOB、 NCLOB、 或 BFILE 适配器还公开从这样的列读取数据的特定操作。 此类操作的名称是 Read_\<LOBColName\>。 例如，如果该视图具有列，规则的类型 BLOB，适配器将公开**Read_RULE**操作。 如果视图具有多个列类型 BLOB、 CLOB、 NCLOB、 或 BFILE 适配器将公开任意多个系列 Read_\<LOBColName\>操作。 请注意该 Update_\<LOBColName\>视图上不支持操作。  
  
## <a name="browsing-for-inbound-operations"></a>浏览的入站操作  
 执行以下步骤以浏览基于项目的视图下的入站的操作。  
  
#### <a name="to-browse-metadata-for-inbound-operations-under-the-artifact-based-view"></a>若要浏览基于项目的视图下的入站操作的元数据  
  
1. 连接到 Oracle E-business Suite 使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 请参阅[连接到在 Visual Studio 中的 Oracle 电子商务套件](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)有关的说明。  
  
2. 从**选择协定类型**列表中，为入站的操作选择**服务 （入站操作）**。  
  
3. **选择一个类别**框中列出的在其下的 Oracle E-business Suite 项目进行分类的不同视图。  
  
    下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 选择根节点 （/），并且可用的根节点下的常规类别节点中列出**可用类别和操作**框。  
  
    ![在根级别的操作的入站](../../adapters-and-accelerators/adapter-oracle-ebs/media/9f9f95f3-c6cc-415c-b534-d5f1ad1963d5.gif "9f9f95f3-c6cc-415c-b534-d5f1ad1963d5")  
  
    入站的操作，**通知**，在根级别也是可用。  
  
4. 展开**基于项目的视图**节点，可以看到，用于 Oracle E-business Suite 和基础数据库项目的类别。 每个类别是进一步分类基于其所属 （适用于 Oracle 电子商务套件项目，例如接口表和界面视图） 的应用程序或 （适用于 Oracle 数据库项目，例如 PL-SQL Api、 过程、 函数所属的架构表和视图）。  
  
   > [!TIP]
   >  您可以直接转到"即时"类别节点或子类别节点在树中，键入项目的名称的树视图中聚焦时**选择一个类别**框。 例如，若要跳转到**过程**节点，重点介绍**基于项目的视图**节点，并键入`Procedures`。  
   > 
   > [!NOTE]
   >  [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不会出现并发程序和请求的入站操作集。  
  
5. 展开 Oracle 应用程序若要查看界面表和界面视图可用于该应用程序的类别。 展开**接口表**并**界面视图**节点以查看界面表和 Oracle 应用程序的界面视图。 单击以查看入站的操作适用的表或视图中的接口表或界面视图**可用类别和操作**框。  
  
    在下图中，在中选择的接口视图**选择一个类别**框和入站的操作支持在视图上被列入**可用类别和操作**框。  
  
    ![界面视图上的操作的入站](../../adapters-and-accelerators/adapter-oracle-ebs/media/937f46f2-d142-413f-8744-2180c7116fd4.gif "937f46f2-d142-413f-8744-2180c7116fd4")  
  
6. 展开**PL-SQL Api**节点以查看类别 （登录与其） 的当前用户架构和基础的 Oracle 数据库中定义的所有其他架构的节点。 展开**当前架构 (\<架构名称\>)** 节点以查看为该架构定义的所有包。 单击要查看的函数和过程中的包中的包名称**可用类别和操作**框。 列出的函数和过程的每个可用于轮询 Oracle 数据库。  
  
    ![浏览 PL&#45;在 Oracle 中的 SQL Api 数据库用于轮询](../../adapters-and-accelerators/adapter-oracle-ebs/media/4b31ea85-9c5a-42b4-82b2-2cb6d3ead35a.gif "4b31ea85-9c5a-42b4-82b2-2cb6d3ead35a")  
  
    同样，展开**所有架构**节点以查看 Oracle 数据库中定义的所有架构的列表。 展开 schema 节点以查看为该架构定义的包的列表。 单击要查看的函数和过程中的包中的包名称**可用类别和操作**框。 列出的函数和过程的每个可用于轮询 Oracle 数据库。  
  
    ![浏览 PL&#45;SQL Api，可用于所有架构的轮询](../../adapters-and-accelerators/adapter-oracle-ebs/media/e28a803e-fcfb-4021-9225-924d54a484c0.gif "e28a803e-fcfb-4021-9225-924d54a484c0")  
  
7. 展开**过程**节点以查看类别 （登录与其） 的当前用户架构和基础的 Oracle 数据库中定义的所有其他架构的节点。 单击**当前架构 (\<架构名称\>)** 节点，查看为该架构中定义的所有过程**可用类别和操作**框。 每个执行下列过程可用于轮询 Oracle 数据库。  
  
    ![浏览所有架构的轮询过程](../../adapters-and-accelerators/adapter-oracle-ebs/media/5e78da80-d99a-44d3-8eac-f636828f8ceb.gif "5e78da80-d99a-44d3-8eac-f636828f8ceb")  
  
    同样，展开**所有架构**节点以查看 Oracle 数据库中定义的所有架构的列表。 单击架构节点以查看为该架构中定义的过程的列表**可用类别和操作**框。 每个执行下列过程可用于轮询 Oracle 数据库。  
  
    ![浏览 Oracle 数据库中的轮询过程](../../adapters-and-accelerators/adapter-oracle-ebs/media/22d8e866-ed19-49f4-a6eb-683343b16cf5.gif "22d8e866-ed19-49f4-a6eb-683343b16cf5")  
  
8. 展开**函数**节点以查看类别 （登录与其） 的当前用户架构和基础的 Oracle 数据库中定义的所有其他架构的节点。 单击**当前架构 (\<架构名称\>)** 节点，查看为该架构中定义的所有函数**可用类别和操作**框。 每个列出的函数可用于轮询 Oracle 数据库。  
  
    ![浏览 Oracle 数据库中的轮询函数](../../adapters-and-accelerators/adapter-oracle-ebs/media/64c0a30d-a2d6-4dee-90cb-a7e7e2bf62cf.gif "64c0a30d-a2d6-4dee-90cb-a7e7e2bf62cf")  
  
    同样，展开**所有架构**节点以查看 Oracle 数据库中定义的所有架构的列表。 单击架构节点以查看为该架构中定义的函数的列表**可用类别和操作**框。  每个列出的函数可用于轮询 Oracle 数据库。  
  
    ![浏览 Oracle 数据库中的轮询函数](../../adapters-and-accelerators/adapter-oracle-ebs/media/1d22c3c8-8c24-4905-8144-bdb4840244f1.gif "1d22c3c8-8c24-4905-8144-bdb4840244f1")  
  
9. 展开**表**节点以查看类别 （登录与其） 的当前用户架构和基础的 Oracle 数据库中定义的所有其他架构的节点。 展开**当前架构 (\<架构名称\>)** 节点可以查看为该架构定义的所有表。 单击表名称可查看**轮询**在此表中支持此操作的入站**可用类别和操作**框。  
  
     ![浏览 Oracle 数据库中的轮询表](../../adapters-and-accelerators/adapter-oracle-ebs/media/7c60dfbf-3836-4e72-abe8-5f32a0936807.gif "7c60dfbf-3836-4e72-abe8-5f32a0936807")  
  
     同样，展开**所有架构**节点以查看 Oracle 数据库中定义的所有架构的列表。 展开 schema 节点以查看为该架构定义的表的列表。 单击表名称可查看**轮询**在此表中支持此操作的入站**可用类别和操作**框。  
  
     ![浏览 Oracle 数据库中的轮询表](../../adapters-and-accelerators/adapter-oracle-ebs/media/c5fbaf59-2e79-4141-8a85-1e1b8eedcea7.gif "c5fbaf59-2e79-4141-8a85-1e1b8eedcea7")  
  
10. 展开**视图**节点以查看类别 （登录与其） 的当前用户架构和基础的 Oracle 数据库中定义的所有其他架构的节点。 展开**当前架构 (\<架构名称\>)** 节点以查看为此定义的所有视图。 单击视图名称可查看**轮询**支持上该视图中操作的入站**可用类别和操作**框。  
  
     ![浏览 Oracle 数据库中的轮询视图](../../adapters-and-accelerators/adapter-oracle-ebs/media/2299de79-9f50-433d-9e71-164f6d02bd78.gif "2299de79-9f50-433d-9e71-164f6d02bd78")  
  
     同样，展开**所有架构**节点以查看 Oracle 数据库中定义的所有架构的列表。 展开 schema 节点以查看为该架构定义的视图的列表。 单击视图名称可查看**轮询**支持上该视图中操作的入站**可用类别和操作**框。  
  
     ![浏览 Oracle 数据库中的轮询视图](../../adapters-and-accelerators/adapter-oracle-ebs/media/860e6636-1ef6-42ad-a0e2-d661e632b624.gif "860e6636-1ef6-42ad-a0e2-d661e632b624")  
  
## <a name="see-also"></a>请参阅  
 [浏览、 搜索和获取 Oracle E-business Suite 操作的元数据](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)