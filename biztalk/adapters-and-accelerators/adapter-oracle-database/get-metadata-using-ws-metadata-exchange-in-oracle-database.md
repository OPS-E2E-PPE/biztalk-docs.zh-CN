---
title: 在 Oracle 数据库中使用 Ws-metadata Exchange 获取元数据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WS-Metadata Exchange, retrieving metadata
- metadata, retrieving using WS-Metadata Exchange
ms.assetid: 6ff34438-7260-489d-a5f0-6e53f8fe43be
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f088e4feadf5d6124ceb7e013d6c991225242b6
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529200"
---
# <a name="get-metadata-using-ws-metadata-exchange-in-oracle-database"></a>在 Oracle 数据库中使用 Ws-metadata Exchange 获取元数据
作为[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]自定义绑定[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]公开可用于检索从特定操作的元数据的 WS-元数据交换 (MEX) 终结点[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]。  
  
 WCF 提供了丰富的基础结构，用于导出、 发布、 检索和导入有关服务的元数据。 WCF 服务，如适配器，使用元数据来描述如何进行交互的服务终结点，以便 svcutil.exe 之类的工具，可以自动生成使用服务的客户端代码。 WCF 服务的元数据表示的实例作为**MetadataSet**类型，它被强附加到定义中 WS-元数据交换 (MEX) 的元数据序列化格式。 您可以创建**MetadataSet**目标上的操作通过使用适配器**MetadataExchangeClient**。  
  
 WCF 支持的元数据交换是一个广泛的主题和此文档的讨论范围之外。 有关 WCF 中的元数据支持的详细信息，请参阅[元数据](https://msdn.microsoft.com/library/ms731823.aspx)。 特别适用的体系结构、 类和命名空间的 WCF 公开元数据的说明，请参阅[元数据体系结构概述](https://msdn.microsoft.com/library/ms730243.aspx)。 您应熟悉与从继续操作之前这些 WCF 主题中的 WCF 服务检索元数据相关的内容。  
  
 以下主题包含有关如何使用信息**MetadataExchangeClient**来检索元数据从[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
## <a name="using-a-metadataexchangeclient-to-retrieve-metadata"></a>使用 MetadataExchangeClient 检索元数据  
 若要使用**MetadataExchangeClient**必须指定连接 URI 和绑定 (**OracleDBBinding**)。 连接 URI 标识你想要检索的元数据的操作。  
  
 以下各节包含有关如何指定连接 URI、 重要的绑定属性，以及如何使用信息**MetadataExchangeClient**从适配器中检索元数据。  
  
### <a name="the-connection-uri"></a>连接 URI  
 若要使用**MetadataExchangeClient**必须提供的 Oracle 连接 URI，指定 MEX 终结点的操作或你想要检索的元数据的操作。 按以下方式，可以在连接 URI 中指定 MEX 终结点和目标操作：  
  
- 您必须在查询字符串中包含"wsdl"参数。 如果它是查询字符串中的第一个参数，则将其指定之后问号 （？）。 如果它不是第一个参数，它应在前面加上 & 号 (&)。  
  
- 必须遵循一个或多个"op"参数"wsdl"的参数。 每个"op"参数的前面有与号 (&)，并指定目标操作的消息操作 (节点 ID)。  
  
  例如，以下连接 URI 中面向 SCOTT 的 Insert 和 Delete 操作。EMP 表。 突出显示的"wsdl"和"op"参数。  
  
```  
"oracledb://ADAPTER?wsdl&op=http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert&op=http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Delete"  
```  
  
> [!NOTE]
>  如果你想要修改为 POLLINGSTMT 操作生成的命名空间则应在查询字符串中指定 PollingId 参数。  
  
 如何将此连接 URI 传递到**MetadataExchangeClient**取决于哪种重载方法用于创建客户端和从适配器检索元数据。  
  
 有关 Oracle 连接 URI 的详细信息，请参阅[创建的 Oracle 数据库连接 URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)。  
  
### <a name="binding-properties"></a>绑定属性  
 当您创建**MetadataExchangeClient**，则必须指定**OracleDBBinding**。  
  
 有几个影响适配器如何生成元数据的绑定属性。 这些属性包括：  
  
-   **EnableSafeTyping**  
  
-   **UseSchemaInNamespace**  
  
-   **PollingStatement**  
  
> [!IMPORTANT]
>  如果你想要检索 POLLINGSTMT 操作的元数据必须设置**PollingStatement**属性绑定。  
  
 应确保这些绑定属性都设置为你的应用程序之前调用所需的值**GetMetadata**方法**MetadataExchangeClient**。 有关详细信息[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]绑定属性，请参阅[阅读有关 Oracle 数据库适配器绑定属性](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)。  
  
### <a name="example"></a>示例  
 下面的示例使用**MetadataExchangeClient**为 Insert、 Update、 Delete 和 SCOTT 的 Select 操作创建服务说明 （WSDL 文档）。EMP 表。 WSDL 将保存到文件，EmpOperations.wsdl。  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
using System.Collections.ObjectModel;  
  
// Needed for WCF and Oracle Adapter  
using System.ServiceModel;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.OracleDB;  
  
// Needced for MetadataExchangeClient class  
using System.ServiceModel.Description;  
// Needed for ServiceDescription class  
using System.Web.Services;  
  
namespace OracleMetadataExchange  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            //create a binding  
            OracleDBBinding binding = new OracleDBBinding();  
  
            //create a metadata exchange client that will retrieve metadata according to the WS-MEX standard  
            MetadataExchangeClient client = new MetadataExchangeClient(binding);  
            client.SoapCredentials.UserName.UserName = "SCOTT";  
            client.SoapCredentials.UserName.Password = "TIGER";  
  
            //set up an endpoint address and specifies the operations for which we want metadata  
            string connectionUri = "oracledb://ADAPTER?wsdl"  
                + "&op="  
                + "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert"  
                + "&op="  
                + "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Update"  
                + "&op="  
                + "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Delete"  
                + "&op="  
                + "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Select";  
  
            EndpointAddress address = new EndpointAddress(connectionUri);  
  
            //get the metadata  
            MetadataSet ms = client.GetMetadata(address);  
  
            // Check for the metadata set size   
            Collection<MetadataSection> documentCollection = ms.MetadataSections;  
            if (documentCollection != null && documentCollection.Count > 0)  
            {  
                //get the wsdl from the metadata set  
                System.Web.Services.Description.ServiceDescription wsdl = (System.Web.Services.Description.ServiceDescription)documentCollection[0].Metadata;  
  
                //save the wsdl to a file  
                wsdl.Write("EmpOperations.wsdl");  
  
            }  
  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>请参阅  
 [从 Oracle 数据库中以编程方式获取元数据](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-programmatically-from-the-oracle-database.md)