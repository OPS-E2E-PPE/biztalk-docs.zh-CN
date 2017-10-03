---
title: "获取使用 Ws-metadata Exchange Oracle 数据库中的元数据 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WS-Metadata Exchange, retrieving metadata
- metadata, retrieving using WS-Metadata Exchange
ms.assetid: 6ff34438-7260-489d-a5f0-6e53f8fe43be
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2be3f829d41b77dc7897d7b3f4300d82e7a3c100
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="get-metadata-using-ws-metadata-exchange-in-oracle-database"></a>获取使用 Ws-metadata Exchange Oracle 数据库中的元数据
作为[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]自定义绑定，[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]公开可用于检索元数据中的特定操作的 WS 元数据交换 (MEX) 终结点[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]。  
  
 WCF 提供了丰富的基础结构，用于导出、 发布、 检索和导入有关服务的元数据。 WCF 服务，例如适配器，使用元数据来描述如何与服务终结点进行交互，以便像 svcutil.exe，这样的工具，可以自动生成使用服务的客户端代码。 WCF 服务的元数据表示实例的形式**MetadataSet**类型，被强附加到定义中 WS 元数据交换 (MEX) 元数据序列化格式。 你可以创建**MetadataSet**目标上的操作使用的适配器**MetadataExchangeClient**。  
  
 WCF 支持元数据交换是广泛主题超出了本文档的范围。 有关在 WCF 中的元数据支持的详细信息，请参阅[元数据](https://msdn.microsoft.com/library/ms731823.aspx)。 体系结构、 类和 WCF 公开的元数据的命名空间的特别好说明，请参阅[元数据体系结构概述](https://msdn.microsoft.com/library/ms730243.aspx)。 你应该熟悉与从之前这些 WCF 主题中的 WCF 服务检索元数据相关的内容。  
  
 以下主题包含有关如何使用信息**MetadataExchangeClient**以检索元数据从[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
## <a name="using-a-metadataexchangeclient-to-retrieve-metadata"></a>使用 MetadataExchangeClient 检索元数据  
 若要使用**MetadataExchangeClient**必须指定连接 URI 和绑定 (**OracleDBBinding**)。 连接 URI 标识你想要检索元数据的操作。  
  
 以下各节提供有关如何指定连接 URI，重要的绑定属性，以及如何使用信息**MetadataExchangeClient**从适配器中检索元数据。  
  
### <a name="the-connection-uri"></a>连接 URI  
 若要使用**MetadataExchangeClient**必须提供的 Oracle 连接 URI，指定 MEX 终结点的操作或你想要检索元数据的操作。 按以下方式，可以在连接 URI 中指定 MEX 终结点和目标操作：  
  
-   你必须查询字符串中包含"wsdl"参数。 如果是查询字符串中的第一个参数，其指定为问号 （？） 之后。 如果它不是第一个参数，它应在它前面加一个与号 (&)。  
  
-   你必须执行一个或多个"op"参数"wsdl"的参数。 每个"op"参数前面是一个与号 (&)，并指定目标操作的消息操作 (节点 ID)。  
  
 例如，以下连接 URI 面向 SCOTT 的 Insert 和 Delete 操作。EMP 表。 突出显示的"wsdl"和"op"参数。  
  
```  
"oracledb://ADAPTER?wsdl&op=http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert&op=http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Delete"  
```  
  
> [!NOTE]
>  如果你想要修改为 POLLINGSTMT 操作生成的命名空间应在查询字符串中指定 PollingId 参数。  
  
 你将此连接 URI 的传递到**MetadataExchangeClient**取决于你用于创建客户端并从适配器检索元数据的重载方法。  
  
 有关 Oracle 连接 URI 的详细信息，请参阅[创建 Oracle 数据库连接 URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)。  
  
### <a name="binding-properties"></a>绑定属性  
 当你创建**MetadataExchangeClient**，必须指定**OracleDBBinding**。  
  
 有几个绑定属性影响如何适配器生成元数据。 这些属性包括：  
  
-   **EnableSafeTyping**  
  
-   **UseSchemaInNamespace**  
  
-   **PollingStatement**  
  
> [!IMPORTANT]
>  如果你想要检索 POLLINGSTMT 操作元数据必须设置**PollingStatement**绑定属性。  
  
 你应确保这些绑定属性被设置为之前调用你的应用程序所需的值**GetMetadata**方法**MetadataExchangeClient**。 有关详细信息[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]绑定属性，请参阅[阅读有关 Oracle 数据库适配器绑定属性](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)。  
  
### <a name="example"></a>示例  
 下面的示例使用**MetadataExchangeClient**为插入、 更新、 删除和 SCOTT 上的 Select 操作创建的服务说明 （WSDL 文档）。EMP 表。 WSDL 保存到文件，EmpOperations.wsdl。  
  
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
  
## <a name="see-also"></a>另请参阅  
 [从 Oracle 数据库以编程方式获取元数据](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-programmatically-from-the-oracle-database.md)