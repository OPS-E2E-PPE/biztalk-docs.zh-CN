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
ms.openlocfilehash: 41b3617afcb595a5ead57118c5b4542d12eb3191
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004014"
---
# <a name="get-metadata-using-ws-metadata-exchange-in-oracle-database"></a><span data-ttu-id="c37be-102">在 Oracle 数据库中使用 Ws-metadata Exchange 获取元数据</span><span class="sxs-lookup"><span data-stu-id="c37be-102">Get Metadata Using WS-Metadata Exchange in Oracle Database</span></span>
<span data-ttu-id="c37be-103">作为[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]自定义绑定[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]公开可用于检索从特定操作的元数据的 WS-元数据交换 (MEX) 终结点[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c37be-103">As a [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] custom binding, the [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] exposes a WS-Metadata Exchange (MEX) endpoint that you can use to retrieve metadata for specific operations from the [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)].</span></span>  
  
 <span data-ttu-id="c37be-104">WCF 提供了丰富的基础结构，用于导出、 发布、 检索和导入有关服务的元数据。</span><span class="sxs-lookup"><span data-stu-id="c37be-104">WCF provides a rich infrastructure for exporting, publishing, retrieving and importing metadata about a service.</span></span> <span data-ttu-id="c37be-105">WCF 服务，如适配器，使用元数据来描述如何进行交互的服务终结点，以便 svcutil.exe 之类的工具，可以自动生成使用服务的客户端代码。</span><span class="sxs-lookup"><span data-stu-id="c37be-105">WCF services, like the adapter, use metadata to describe how to interact with the service endpoints so that tools, like svcutil.exe, can automatically generate client code for consuming the service.</span></span> <span data-ttu-id="c37be-106">WCF 服务的元数据表示的实例作为**MetadataSet**类型，它被强附加到定义中 WS-元数据交换 (MEX) 的元数据序列化格式。</span><span class="sxs-lookup"><span data-stu-id="c37be-106">WCF represents the metadata for a service as an instance of the **MetadataSet** type, which is strongly tied to the metadata serialization format defined in WS-Metadata Exchange (MEX).</span></span> <span data-ttu-id="c37be-107">您可以创建**MetadataSet**目标上的操作通过使用适配器**MetadataExchangeClient**。</span><span class="sxs-lookup"><span data-stu-id="c37be-107">You can create a **MetadataSet** for targeted operations on the adapter by using a **MetadataExchangeClient**.</span></span>  
  
 <span data-ttu-id="c37be-108">WCF 支持的元数据交换是一个广泛的主题和此文档的讨论范围之外。</span><span class="sxs-lookup"><span data-stu-id="c37be-108">WCF support for metadata exchange is an expansive topic and beyond the scope of this documentation.</span></span> <span data-ttu-id="c37be-109">有关 WCF 中的元数据支持的详细信息，请参阅[元数据](https://msdn.microsoft.com/library/ms731823.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c37be-109">For more information about support for metadata in WCF, see [Metadata](https://msdn.microsoft.com/library/ms731823.aspx).</span></span> <span data-ttu-id="c37be-110">特别适用的体系结构、 类和命名空间的 WCF 公开元数据的说明，请参阅[元数据体系结构概述](https://msdn.microsoft.com/library/ms730243.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c37be-110">For a particularly good description of the architecture, classes, and namespaces that WCF exposes for metadata, see [Metadata Architecture Overview](https://msdn.microsoft.com/library/ms730243.aspx).</span></span> <span data-ttu-id="c37be-111">您应熟悉与从继续操作之前这些 WCF 主题中的 WCF 服务检索元数据相关的内容。</span><span class="sxs-lookup"><span data-stu-id="c37be-111">You should familiarize yourself with the content related to retrieving metadata from a WCF service in these WCF topics before proceeding.</span></span>  
  
 <span data-ttu-id="c37be-112">以下主题包含有关如何使用信息**MetadataExchangeClient**来检索元数据从[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c37be-112">The following topics contain information about how to use a **MetadataExchangeClient** to retrieve metadata from the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
## <a name="using-a-metadataexchangeclient-to-retrieve-metadata"></a><span data-ttu-id="c37be-113">使用 MetadataExchangeClient 检索元数据</span><span class="sxs-lookup"><span data-stu-id="c37be-113">Using a MetadataExchangeClient to Retrieve Metadata</span></span>  
 <span data-ttu-id="c37be-114">若要使用**MetadataExchangeClient**必须指定连接 URI 和绑定 (**OracleDBBinding**)。</span><span class="sxs-lookup"><span data-stu-id="c37be-114">To use a **MetadataExchangeClient** you must specify a connection URI and a binding (**OracleDBBinding**).</span></span> <span data-ttu-id="c37be-115">连接 URI 标识你想要检索的元数据的操作。</span><span class="sxs-lookup"><span data-stu-id="c37be-115">The connection URI identifies the operations for which you want to retrieve metadata.</span></span>  
  
 <span data-ttu-id="c37be-116">以下各节包含有关如何指定连接 URI、 重要的绑定属性，以及如何使用信息**MetadataExchangeClient**从适配器中检索元数据。</span><span class="sxs-lookup"><span data-stu-id="c37be-116">The following sections contain information about how to specify the connection URI, important binding properties, and how to use a **MetadataExchangeClient** to retrieve metadata from the adapter.</span></span>  
  
### <a name="the-connection-uri"></a><span data-ttu-id="c37be-117">连接 URI</span><span class="sxs-lookup"><span data-stu-id="c37be-117">The Connection URI</span></span>  
 <span data-ttu-id="c37be-118">若要使用**MetadataExchangeClient**必须提供的 Oracle 连接 URI，指定 MEX 终结点的操作或你想要检索的元数据的操作。</span><span class="sxs-lookup"><span data-stu-id="c37be-118">To use the **MetadataExchangeClient** you must supply an Oracle connection URI that specifies a MEX endpoint and the operation or operations for which you want to retrieve metadata.</span></span> <span data-ttu-id="c37be-119">按以下方式，可以在连接 URI 中指定 MEX 终结点和目标操作：</span><span class="sxs-lookup"><span data-stu-id="c37be-119">You specify a MEX endpoint and target operations in the connection URI in the following manner:</span></span>  
  
- <span data-ttu-id="c37be-120">您必须在查询字符串中包含"wsdl"参数。</span><span class="sxs-lookup"><span data-stu-id="c37be-120">You must include the "wsdl" parameter in the query string.</span></span> <span data-ttu-id="c37be-121">如果它是查询字符串中的第一个参数，则将其指定之后问号 （？）。</span><span class="sxs-lookup"><span data-stu-id="c37be-121">If it is the first parameter in the query string, it is specified just after the question mark (?).</span></span> <span data-ttu-id="c37be-122">如果它不是第一个参数，它应在前面加上 & 号 (&)。</span><span class="sxs-lookup"><span data-stu-id="c37be-122">If it is not the first parameter, it should be preceded with an ampersand (&).</span></span>  
  
- <span data-ttu-id="c37be-123">必须遵循一个或多个"op"参数"wsdl"的参数。</span><span class="sxs-lookup"><span data-stu-id="c37be-123">You must follow the "wsdl" parameter by one or more "op" parameters.</span></span> <span data-ttu-id="c37be-124">每个"op"参数的前面有与号 (&)，并指定目标操作的消息操作 (节点 ID)。</span><span class="sxs-lookup"><span data-stu-id="c37be-124">Each "op" parameter is preceded by an ampersand (&) and specifies the message action (node ID) of a target operation.</span></span>  
  
  <span data-ttu-id="c37be-125">例如，以下连接 URI 中面向 SCOTT 的 Insert 和 Delete 操作。EMP 表。</span><span class="sxs-lookup"><span data-stu-id="c37be-125">For example, the following connection URI targets the Insert and Delete operations for the SCOTT.EMP table.</span></span> <span data-ttu-id="c37be-126">突出显示的"wsdl"和"op"参数。</span><span class="sxs-lookup"><span data-stu-id="c37be-126">The "wsdl" and "op" parameters are highlighted.</span></span>  
  
```  
"oracledb://ADAPTER?wsdl&op=http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert&op=http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Delete"  
```  
  
> [!NOTE]
>  <span data-ttu-id="c37be-127">如果你想要修改为 POLLINGSTMT 操作生成的命名空间则应在查询字符串中指定 PollingId 参数。</span><span class="sxs-lookup"><span data-stu-id="c37be-127">If you want to modify the namespace generated for the POLLINGSTMT operation you should specify a PollingId parameter in the query string.</span></span>  
  
 <span data-ttu-id="c37be-128">如何将此连接 URI 传递到**MetadataExchangeClient**取决于哪种重载方法用于创建客户端和从适配器检索元数据。</span><span class="sxs-lookup"><span data-stu-id="c37be-128">How you pass this connection URI to the **MetadataExchangeClient** depends on which of the overloaded methods you use to create the client and retrieve metadata from the adapter.</span></span>  
  
 <span data-ttu-id="c37be-129">有关 Oracle 连接 URI 的详细信息，请参阅[创建的 Oracle 数据库连接 URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="c37be-129">For more information about the Oracle connection URI, see [Create the Oracle Database connection URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).</span></span>  
  
### <a name="binding-properties"></a><span data-ttu-id="c37be-130">绑定属性</span><span class="sxs-lookup"><span data-stu-id="c37be-130">Binding Properties</span></span>  
 <span data-ttu-id="c37be-131">当您创建**MetadataExchangeClient**，则必须指定**OracleDBBinding**。</span><span class="sxs-lookup"><span data-stu-id="c37be-131">When you create the **MetadataExchangeClient**, you must specify an **OracleDBBinding**.</span></span>  
  
 <span data-ttu-id="c37be-132">有几个影响适配器如何生成元数据的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="c37be-132">There are several binding properties that affect how the adapter generates metadata.</span></span> <span data-ttu-id="c37be-133">这些属性包括：</span><span class="sxs-lookup"><span data-stu-id="c37be-133">These properties are:</span></span>  
  
-   <span data-ttu-id="c37be-134">**EnableSafeTyping**</span><span class="sxs-lookup"><span data-stu-id="c37be-134">**EnableSafeTyping**</span></span>  
  
-   <span data-ttu-id="c37be-135">**UseSchemaInNamespace**</span><span class="sxs-lookup"><span data-stu-id="c37be-135">**UseSchemaInNamespace**</span></span>  
  
-   <span data-ttu-id="c37be-136">**PollingStatement**</span><span class="sxs-lookup"><span data-stu-id="c37be-136">**PollingStatement**</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c37be-137">如果你想要检索 POLLINGSTMT 操作的元数据必须设置**PollingStatement**属性绑定。</span><span class="sxs-lookup"><span data-stu-id="c37be-137">If you want to retrieve metadata for the POLLINGSTMT operation you must set the **PollingStatement** binding property.</span></span>  
  
 <span data-ttu-id="c37be-138">应确保这些绑定属性都设置为你的应用程序之前调用所需的值**GetMetadata**方法**MetadataExchangeClient**。</span><span class="sxs-lookup"><span data-stu-id="c37be-138">You should ensure that these binding properties are set to the values required for your application before you invoke the **GetMetadata** method on the **MetadataExchangeClient**.</span></span> <span data-ttu-id="c37be-139">有关详细信息[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]绑定属性，请参阅[阅读有关 Oracle 数据库适配器绑定属性](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="c37be-139">For more information about the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] binding properties, see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span>  
  
### <a name="example"></a><span data-ttu-id="c37be-140">示例</span><span class="sxs-lookup"><span data-stu-id="c37be-140">Example</span></span>  
 <span data-ttu-id="c37be-141">下面的示例使用**MetadataExchangeClient**为 Insert、 Update、 Delete 和 SCOTT 的 Select 操作创建服务说明 （WSDL 文档）。EMP 表。</span><span class="sxs-lookup"><span data-stu-id="c37be-141">The following example uses a **MetadataExchangeClient** to create a service description (WSDL document) for the Insert, Update, Delete, and Select operations on the SCOTT.EMP table.</span></span> <span data-ttu-id="c37be-142">WSDL 将保存到文件，EmpOperations.wsdl。</span><span class="sxs-lookup"><span data-stu-id="c37be-142">The WSDL is saved to a file, EmpOperations.wsdl.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c37be-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="c37be-143">See Also</span></span>  
 [<span data-ttu-id="c37be-144">从 Oracle 数据库中以编程方式获取元数据</span><span class="sxs-lookup"><span data-stu-id="c37be-144">Get Metadata Programmatically from the Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-programmatically-from-the-oracle-database.md)