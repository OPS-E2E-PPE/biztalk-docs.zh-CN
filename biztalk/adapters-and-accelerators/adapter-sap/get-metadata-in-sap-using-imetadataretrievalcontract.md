---
title: 在 SAP 中使用 IMetadataRetrievalContract 获取元数据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- how to, search metadata
- searching metadata
- how to, browse metadata
- browsing metadata
ms.assetid: 0944fc39-9ee5-4702-8b52-e0bc87f202c6
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9ff0828635b16cfc94d134f17e5210a255e862a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007462"
---
# <a name="get-metadata-in-sap-using-imetadataretrievalcontract"></a>在 SAP 中使用 IMetadataRetrievalContract 获取元数据
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]公开**IMetadataRetrievalContract**浏览和搜索 SAP 系统项目以及如何检索有关 Web 服务描述语言 (WSDL) 文档的窗体中的元数据可以使用的终结点操作。  
  
 **IMetadataRetrievalContract**接口由实现[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]，并提供元数据浏览、 搜索和检索功能。 除了**IMetadataRetrievalContract**接口，[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]公开**MetadataRetrievalClient**类，该类实现接口。 你可以使用**IMetadataRetrievalContract**通道或**MetadataRetrievalClient**以使用元数据; 浏览、 搜索和检索元数据公开的方法是相同的每种情况下。  
  
 以下部分提供有关如何使用信息**IMetadataRetrievalContract**接口。  
  
## <a name="the-imetadataretrievalcontract-interface"></a>IMetadataRetrievalContract 接口  
 下表提供了有关在使用时使用的重要类的信息**IMetadataRetrievalContract**接口。  
  
|类或接口|Description|  
|------------------------|-----------------|  
|**IMetadataRetrievalContract**接口<br /><br /> (Microsoft.ServiceModel.Channels)|定义**浏览**，**搜索**，并**GetMetadata**方法。 调用这些方法是通过**IMetadataRetrievalContract**通道或**MetadataRetrievalClient**若要使用的适配器元数据。|  
|**MetadataRetrievalClient**类<br /><br /> (Microsoft.ServiceModel.Channels)|实现**IMetadataRetrievalContract**接口。 您可以创建此类的实例并将其配置为 SAP 系统，从而**SAPBinding**和一个**EndpointAddress**。 然后可以调用其方法来处理的元数据。|  
|**MetadataRetrievalNode**类<br /><br /> (Microsoft.ServiceModel.Channels)|表示在适配器上的元数据节点。 **浏览**并**搜索**方法将返回此类型的节点和**GetMetadata**方法采用一个参数为此类型的节点。|  
|**ServiceDescription**类<br /><br /> (System.Web.Services.Description)|提供了一种创建和格式设置的有效的 WSDL 文档文件。 **GetMetadata**方法将返回**ServiceDescription**对象。|  
  
 有关详细信息**IMetadataRetrievalContract**接口， **MetadataRetrievalClient**类，并且**MetadataRetrievalNode**类; 请参阅**Microsoft.ServiceModel.Channels**托管在参考[ http://go.microsoft.com/fwlink/?LinkId=105566 ](http://go.microsoft.com/fwlink/?LinkId=105566)。  
  
### <a name="metadata-node-ids"></a>元数据节点 Id  
 该适配器将其元数据组织为层次结构树的节点。 在此树结构中，有两种类型的元数据节点：  
  
- **操作节点**表示，它会将适配器显示在 SAP 项目上的操作。 操作节点均为树的叶。  
  
- **类别节点**表示 SAP 项目并不直接对应的 SAP 项目的分组到在适配器上的操作。 类别节点是树的分支它们包含其他类别节点和/或操作节点。 例如，RFC 功能组或 SAP 业务对象表示为类别节点。  
  
  适配器提供的每个元数据节点标识的唯一节点 id。 有关元数据节点 Id 适配器提供的详细信息，请参阅[元数据节点 Id](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md)。 使用这些节点 Id 来使用时，指定目标 SAP 项目**IMetadataRetrievalContract**接口以浏览、 搜索和检索元数据。 可以使用中定义的常量`Microsoft.Adapters.SAP.SAPAdapterConstants.MetadataConstants`和`Microsoft.Adapters.SAP.SAPAdapterConstants.ActionConstants`来帮助您构造元数据节点 Id。  
  
### <a name="binding-properties"></a>绑定属性  
 无论是使用**IMetadataRetrievalContract**通道或**IMetadataRetrievalClient**若要使用的元数据，必须指定**SAPBinding**创建时实例。  
  
 有几个影响适配器如何生成元数据的绑定属性。 这些属性包括：  
  
- **GenerateFlatfileCompatibleIdocSchema**  
  
- **ReceiveIDocFormat**  
  
- **EnableSafeTyping**  
  
- **FlatFileSegmentIndicator**  
  
  应确保这些绑定属性设置为所需的应用程序之前打开元数据检索对象的值。 有关 SAP 适配器绑定属性的详细信息，请参阅[了解用于 mySAP Business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。  
  
### <a name="browsing-metadata-nodes"></a>浏览元数据节点  
 您使用**浏览**方法以返回所包含的所有元数据节点中的父节点。 下面的示例浏览 SAP 系统上的前三个 RFC 功能组。 在此示例中，**客户端**的一个实例**MetadataRetrievalClient**。  
  
```  
// The first parameter is the node ID.   
// The second parameter is the start index.  
// The third parameter is the maximum number of nodes to return.  
IMetadataRetrievalNode[] nodes = client.Browse(Microsoft.Adapters.SAP.SAPAdapterConstants.MetadataConstants.RfcSection, 0, 3);  
```  
  
> [!IMPORTANT]
>  您只能浏览类别节点，则无法浏览操作节点。  
  
### <a name="searching-for-metadata-nodes"></a>搜索元数据节点  
 您使用**搜索**方法来执行所包含的父节点的节点的搜索。 您可以指定星号 (\*) 通配符字符。 此字符匹配零个或多个字符。 下面的示例演示搜索包含字符串"BAPI"的所有 Rfc。 在此示例中，**客户端**的一个实例**MetadataRetrievalClient**。  
  
```  
// Search for all nodes that contain "BAPI" under the RFC node.  
// The parameters are the parent node ID, the search expression, and   
// the maximum number of nodes to return.  
IMetadataRetrievalNode[] nodes = client.Search(Microsoft.Adapters.SAP.SAPAdapterConstants.MetadataConstants.RfcSection, "*BAPI*", int.MaxValue);  
```  
  
> [!IMPORTANT]
>  仅支持有限的一组节点上进行搜索。 有关在其支持搜索的节点以及搜索表达式中支持的通配符字符的详细信息，请参阅[元数据节点 Id](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md)。  
  
### <a name="retrieving-metadata-wsdl-for-operations"></a>检索操作的元数据 (WSDL)  
 您使用**GetMetadata**方法来检索服务说明 （WSDL 文档） 的一组的操作节点。 下面的示例检索 BAPI_TRANSACTION_COMMIT RFC 服务说明。 在此示例中，**客户端**的一个实例**MetadataRetrievalClient**。 请注意，等效于该操作的消息操作的操作节点的节点 ID。  
  
```  
// Get a WSDL document that specifies a contract that contains the  
// BAPI_TRANSACTION_COMMIT operation.  
MetadataRetrievalNode[] nodes = new MetadataRetrievalNode[1];  
nodes[0] = new MetadataRetrievalNode();  
nodes[0].NodeId = Microsoft.Adapters.SAP.SAPAdapterConstants.ActionConstants.RfcActionPrefix + "BAPI_TRANSACTION_COMMIT";  
nodes[0].IsOperation = true;  
  
System.Web.Services.Description.ServiceDescription description = client.GetMetadata(nodes);  
```  
  
> [!IMPORTANT]
>  只应指定操作中的节点**GetMetadata**方法。  
  
### <a name="using-a-metadataretrievalclient"></a>使用 MetadataRetrievalClient  
 创建和使用**MetadataRetrievalClient**是任何其他 WCF 客户端，大致相同。 通过指定终结点和的实例创建客户端**SAPBinding**。 可以以声明方式在配置中或在代码中以强制方式执行此操作。 然后，可以调用的方法**MetadataRetrievalClient**浏览、 搜索和检索来自适配器的元数据。  
  
 下面的示例演示如何使用**MetadataRetrievalClient**以浏览、 搜索和检索元数据从[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using System.ServiceModel;  
using Microsoft.Adapters.SAP;  
using Microsoft.ServiceModel.Channels;  
  
using System.Web.Services.Description;  
  
namespace SapMetaDataBrowseClient  
{  
    class NodeWriter  
    {  
        // This method writes the value of a collection of metadata retrieval nodes  
        // to the console.  
        public void Write(string title, MetadataRetrievalNode[] nodes)  
        {  
            Console.WriteLine(title);  
            Console.WriteLine();  
  
            //Write all the nodes returned to the console.  
            foreach (MetadataRetrievalNode node in nodes)  
            {  
                Console.WriteLine("NodeId = " + node.NodeId);  
                Console.WriteLine("\tDirection   = " + node.Direction.ToString());  
                Console.WriteLine("\tIsOperation = " + node.IsOperation.ToString());  
                Console.WriteLine("\tDisplayName = " + node.DisplayName);  
                Console.WriteLine("\tDescription = " + node.Description);  
            }  
            Console.WriteLine();  
        }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            MetadataRetrievalClient browser = null;  
            NodeWriter nodeWriter = new NodeWriter();  
  
            try  
            {  
                // Create a binding  
                SAPBinding binding = new SAPBinding();  
  
                EndpointAddress address = new EndpointAddress("sap://Client=800;lang=EN@A/YourSAPHost/00");  
  
                browser = new MetadataRetrievalClient(binding, address);  
                browser.ClientCredentials.UserName.UserName = "YourUserName";  
                browser.ClientCredentials.UserName.Password = "YourPassword";  
                browser.Open();  
  
                // Return the nodes directly under the root.  
                // The parameters are the parent node ID, the start index, and the maximum number  
                // of nodes to return.  
                MetadataRetrievalNode[] nodes = browser.Browse(MetadataRetrievalNode.Root.NodeId, 0, int.MaxValue);  
                nodeWriter.Write("Browse results for the root node:", nodes);  
  
                // Return first 3 RFC group nodes.  
                nodes = browser.Browse(Microsoft.Adapters.SAP.SAPAdapterConstants.MetadataConstants.RfcSection, 0, 3);  
                nodeWriter.Write(String.Format("Browse results for the first {1} nodes of {0}:", Microsoft.Adapters.SAP.SAPAdapterConstants.MetadataConstants.RfcSection, nodes.Length), nodes);  
  
                // Search for first 3 nodes that begin with "BAPI_TRANSACTION" under the RFC node.  
                // The parameters are the parent node ID, the search expression, and the maximum number  
                // of nodes to return.  
                nodes = browser.Search(Microsoft.Adapters.SAP.SAPAdapterConstants.MetadataConstants.RfcSection, "*BAPI_TRANSACTION*", 3);  
                nodeWriter.Write(String.Format("Search results for \"*BAPI_TRANSACTION*\" under {0} node:", Microsoft.Adapters.SAP.SAPAdapterConstants.MetadataConstants.RfcSection), nodes);  
  
                // Get a WSDL document that specifies a contract that contains the operations  
                // found in the search and write it to a file.  
                // You could explicitly specify operations as in the following:  
                //    nodes[0] = new MetadataRetrievalNode();  
                //    nodes[0].NodeId = Microsoft.Adapters.SAP.SAPAdapterConstants.ActionConstants.RfcActionPrefix + "BAPI_TRANSACTION_COMMIT";  
                //    nodes[0].IsOperation = true;  
                // Note that the operation NodeId is equivalent to the message action.  
                System.Web.Services.Description.ServiceDescription description = browser.GetMetadata(nodes);  
                description.Write("SampleContract.wsdl");  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine("Exception is: " + ex.Message);  
            }  
            finally  
            {  
                if (browser != null)  
                {  
                    if (browser.State == CommunicationState.Opened)  
                        browser.Close();  
                    else  
                        browser.Abort();  
                }  
            }  
        }  
    }  
}  
```  
  
 下图显示在控制台上该程序的输出。 可以看到为每个方法返回的元数据检索节点的结构。 该程序还将写入描述包含到文件中搜索所返回的节点的服务协定的 WSDL 文档。 （对于大多数 SAP 安装，服务说明将包含 BAPI_TRANSACTION_COMMIT 和 BAPI_TRANSACTION_ROLLBACK 操作。）  
  
```  
Browse results for the root node:  
  
NodeId = http://Microsoft.LobServices.Sap/2007/03/BAPISECTION/000001  
        Direction   = Outbound  
        IsOperation = False  
        DisplayName = BAPI  
        Description = BAPI  
NodeId = http://Microsoft.LobServices.Sap/2007/03/IDOCSECTION/  
        Direction   = Inbound, Outbound  
        IsOperation = False  
        DisplayName = IDOC  
        Description = IDOC  
NodeId = http://Microsoft.LobServices.Sap/2007/03/RFCSECTION/  
        Direction   = Inbound, Outbound  
        IsOperation = False  
        DisplayName = RFC  
        Description = RFC  
NodeId = http://Microsoft.LobServices.Sap/2007/03/TRFCSECTION/  
        Direction   = Inbound, Outbound  
        IsOperation = False  
        DisplayName = TRFC  
        Description = TRFC  
  
Browse results for the first 3 nodes of http://Microsoft.LobServices.Sap/2007/03  
/RFCSECTION/:  
  
NodeId = http://Microsoft.LobServices.Sap/2007/03/RFCGROUP/A  
        Direction   = Inbound, Outbound  
        IsOperation = False  
        DisplayName = Asset Accounting  
        Description = Asset Accounting  
NodeId = http://Microsoft.LobServices.Sap/2007/03/RFCGROUP/S  
        Direction   = Inbound, Outbound  
        IsOperation = False  
        DisplayName = Basis  
        Description = Basis  
NodeId = http://Microsoft.LobServices.Sap/2007/03/RFCGROUP/B  
        Direction   = Inbound, Outbound  
        IsOperation = False  
        DisplayName = Business Information Warehouse  
        Description = Business Information Warehouse  
  
Search results for "*BAPI_TRANSACTION*" under http://Microsoft.LobServices.Sap/2  
007/03/RFCSECTION/ node:  
  
NodeId = http://Microsoft.LobServices.Sap/2007/03/Rfc/BAPI_TRANSACTION_COMMIT  
        Direction   = Inbound, Outbound  
        IsOperation = True  
        DisplayName = BAPI_TRANSACTION_COMMIT  
        Description = Execute external Commit when using BAPIs  
NodeId = http://Microsoft.LobServices.Sap/2007/03/Rfc/BAPI_TRANSACTION_ROLLBACK  
        Direction   = Inbound, Outbound  
        IsOperation = True  
        DisplayName = BAPI_TRANSACTION_ROLLBACK  
        Description = Execute external Rollback when using BAPIs  
  
```  
  
## <a name="using-an-imetadataretrievalcontract-channel"></a>使用 IMetadataRetrievalContract 通道  
 此外可以创建**IMetadataRetrievalContract**通道，然后使用此通道来浏览、 搜索和检索来自适配器的元数据。 (方法签名均为适用于**MetadataRetrievalClient**类。)下面的示例演示如何执行此操作。  
  
```  
…  
//Create a binding and endpoint address.  
SAPBinding binding = new SAPBinding();  
EndpointAddress address = new EndpointAddress("sap://Client=800;lang=EN@A/YourSAPHost/00");  
  
//Create and open a channel factory that will return an IMetadataRetrievalContract object, on which browse, search, and get can be performed.  
ChannelFactory<IMetadataRetrievalContract> factory = new ChannelFactory<IMetadataRetrievalContract>(binding, address);  
factory.Credentials.UserName.UserName = "YourUserName";  
factory.Credentials.UserName.Password = "YourPassword";  
factory.Open();  
  
//Obtain an IMetadataRetrievalContract channel from the factory.  
IMetadataRetrievalContract channel = factory.CreateChannel();  
  
//Perform a search using the channel.  
MetadataRetrievalNode[] nodes = channel.Search(Microsoft.Adapters.SAP.SAPAdapterConstants.MetadataConstants.RfcSection, "BAPI_TRANSACTION*", int.MaxValue);  
…  
```  
  
## <a name="see-also"></a>请参阅  
 [以编程方式从 SAP 检索元数据](../../adapters-and-accelerators/adapter-sap/get-metadata-programmatically-from-sap.md)