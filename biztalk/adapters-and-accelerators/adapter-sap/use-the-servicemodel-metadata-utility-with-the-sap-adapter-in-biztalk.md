---
title: 使用 ServiceModel 元数据实用工具 BizTalk 适配器为 mySAP Business Suite |Microsoft 文档
description: 使用 svcutil.exe，对于非默认绑定，或使用 SAP 适配器-BizTalk 适配器包 (BAP) 中创建的 WCF 客户端类或 WCF 服务协定
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ServiceModel Metadata Utility Tool, creating a WCF Client Class or a WCF service contract with the tool
- ServiceModel Metadata Utility Tool, configuring the tool for the adapter
ms.assetid: 7ac08012-bb12-4983-9402-be84fe3997d8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15c4612db6e3cde4e46385b1c5d1810fbb00eb70
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
ms.locfileid: "25962763"
---
# <a name="using-the-servicemodel-metadata-utility-tool-with-the-biztalk-adapter-for-mysap-business-suite"></a><span data-ttu-id="13a10-103">为 mySAP Business Suite 中使用 BizTalk 适配器使用 ServiceModel 元数据实用工具</span><span class="sxs-lookup"><span data-stu-id="13a10-103">Using the ServiceModel Metadata Utility Tool with the BizTalk Adapter for mySAP Business Suite</span></span>
<span data-ttu-id="13a10-104">你可以使用 ServiceModel 元数据实用工具 (svcutil.exe) 生成 WCF 客户端类或操作的 WCF 服务协定 （接口），[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]公开。</span><span class="sxs-lookup"><span data-stu-id="13a10-104">You can use the ServiceModel Metadata Utility Tool (svcutil.exe) to generate a WCF client class or a WCF service contract (interface) for operations that the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] exposes.</span></span> <span data-ttu-id="13a10-105">运行 svcutil.exe 以生成 WCF 客户端类或 WCF 服务协定后，您可以在你的代码中包含生成的文件和创建生成的类的实例或实现 WCF 服务生成的接口在 SAP 上执行操作系统。</span><span class="sxs-lookup"><span data-stu-id="13a10-105">After you run svcutil.exe to generate either a WCF client class or a WCF service contract, you can include the generated file in your code and create instances of the generated class or implement a WCF service from the generated interface to perform operations on the SAP system.</span></span>  
  
 <span data-ttu-id="13a10-106">使用 svcutil.exe 需要你提供一个连接 URI，其中包含凭据。</span><span class="sxs-lookup"><span data-stu-id="13a10-106">Using svcutil.exe requires you to supply a connection URI that contains credentials.</span></span> <span data-ttu-id="13a10-107">因为，默认情况下，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]禁用凭据在连接 URI，你必须配置要使用的非默认绑定的 svcutil.exe [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="13a10-107">Because, by default, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] disables credentials in the connection URI, you must configure svcutil.exe to use a non-default binding for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="13a10-108">你还可以在非默认绑定; 中配置其他绑定属性例如，若要创建 WCF 客户端 BAPI 操作，你必须设置**EnableSafeTyping**属性绑定到**true**。</span><span class="sxs-lookup"><span data-stu-id="13a10-108">You can also configure other binding properties in the non-default binding; for example, to create a WCF client for BAPI operations, you must set the **EnableSafeTyping** binding property to **true**.</span></span>  
  
 <span data-ttu-id="13a10-109">以下部分说明如何配置 svcutil.exe 以及如何使用 svcutil.exe 生成 WCF 客户端代码或 WCF 服务协定与[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="13a10-109">The following sections show you how to configure svcutil.exe and how to use svcutil.exe to generate WCF client code or a WCF service contract with the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
##  <a name="BKMK_ConfigureSvcutil"></a> <span data-ttu-id="13a10-110">为 SAP 适配器配置 svcutil.exe</span><span class="sxs-lookup"><span data-stu-id="13a10-110">Configuring svcutil.exe for the SAP Adapter</span></span>  
 <span data-ttu-id="13a10-111">若要配置为使用非默认绑定的 svcutil.exe，你必须创建 svcutil.exe 的本地副本，然后创建或修改 svcutil.exe.config 配置文件的本地副本。</span><span class="sxs-lookup"><span data-stu-id="13a10-111">To configure svcutil.exe to use a non-default binding, you must create a local copy of svcutil.exe and then create or modify a local copy of the svcutil.exe.config configuration file.</span></span>  
  
1.  <span data-ttu-id="13a10-112">创建一个文件夹，并将 svcutil.exe 复制到新文件夹。</span><span class="sxs-lookup"><span data-stu-id="13a10-112">Create a folder, and copy svcutil.exe into the new folder.</span></span> <span data-ttu-id="13a10-113">你通常可以找到 svcutil.exe 在 Windows SDK 安装位置，具体而言，C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin。</span><span class="sxs-lookup"><span data-stu-id="13a10-113">You can typically find svcutil.exe at the Windows SDK installation location, specifically, C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin.</span></span>  
  
2.  <span data-ttu-id="13a10-114">创建名为的新文件夹中的 svcutil.exe.config 的文件。</span><span class="sxs-lookup"><span data-stu-id="13a10-114">Create a file named svcutil.exe.config in the new folder.</span></span>  
  
3.  <span data-ttu-id="13a10-115">将一个绑定和客户端终结点添加到 svcutil.exe.config 文件中。</span><span class="sxs-lookup"><span data-stu-id="13a10-115">Add a binding and a client endpoint to the svcutil.exe.config file.</span></span> <span data-ttu-id="13a10-116">你必须从新的文件夹，以确保使用正确的配置运行 svcutil.exe。</span><span class="sxs-lookup"><span data-stu-id="13a10-116">You must run svcutil.exe from the new folder to ensure that the correct configuration is used.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="13a10-117">客户端终结点的名称属性必须指定连接 URI 中所使用的方案。</span><span class="sxs-lookup"><span data-stu-id="13a10-117">The name attribute of the client endpoint must specify the scheme used in the connection URI.</span></span> <span data-ttu-id="13a10-118">此值区分大小写。</span><span class="sxs-lookup"><span data-stu-id="13a10-118">This value is case-sensitive.</span></span>  
  
    ```  
    <configuration>  
      <system.serviceModel>  
        <client>  
          <!-- the name should match the required scheme of the WS-Metadata Exchange endpoint   
          and the contract should be "IMetadataExchange" -->  
          <endpoint name="sap"  
                    binding="sapBinding"  
                    bindingConfiguration="SAPBinding"  
                    contract="IMetadataExchange" />  
        </client>  
        <bindings>  
          <sapBinding>  
            <binding name="SAPBinding" acceptCredentialsInUri="true"/>  
          </sapBinding>  
        </bindings>  
  
      </system.serviceModel>  
  
    </configuration>  
    ```  
  
 <span data-ttu-id="13a10-119">你可以设置的绑定属性的任何[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]在绑定配置。</span><span class="sxs-lookup"><span data-stu-id="13a10-119">You can set any of the binding properties of the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] in the binding configuration.</span></span> <span data-ttu-id="13a10-120">例如，你可以指定以下的非默认绑定，以使用 svcutil.exe 生成 WCF 客户端 BAPI 操作。</span><span class="sxs-lookup"><span data-stu-id="13a10-120">For example, you could specify the following non-default binding to use svcutil.exe to generate a WCF client for BAPI operations.</span></span>  
  
```  
<bindings>  
  <sapBinding>  
    <binding name="SAPBinding" acceptCredentialsInUri="true"/>  
  </sapBinding>  
</bindings>  
```  
  
 <span data-ttu-id="13a10-121">有关配置 svcutil.exe 的非默认绑定的详细信息，请参阅[自定义安全元数据终结点](https://msdn.microsoft.com/library/aa395212.aspx)。</span><span class="sxs-lookup"><span data-stu-id="13a10-121">For more information about configuring a non-default binding for svcutil.exe, see the [Custom Secure Metadata Endpoint](https://msdn.microsoft.com/library/aa395212.aspx).</span></span>
  
## <a name="creating-a-wcf-client-class-or-a-wcf-service-contract-with-svcutilexe"></a><span data-ttu-id="13a10-122">使用 svcutil.exe 创建 WCF 客户端类或 WCF 服务协定</span><span class="sxs-lookup"><span data-stu-id="13a10-122">Creating a WCF Client Class or a WCF Service Contract with svcutil.exe</span></span>  
 <span data-ttu-id="13a10-123">以使用 svcutil.exe 来生成 WCF 客户端代码或 WCF 服务协定 （接口） [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，你必须提供连接 URI，指定 WS 元数据交换 (MEX) 终结点的操作或你想到 svcutil.exe 的操作生成代码。</span><span class="sxs-lookup"><span data-stu-id="13a10-123">To use svcutil.exe to generate WCF client code or a WCF service contract (interface) for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], you must supply a connection URI that specifies a WS-Metadata Exchange (MEX) endpoint and the operation or operations for which you want svcutil.exe to generate code.</span></span> <span data-ttu-id="13a10-124">此外必须在连接 URI 中指定的 SAP 系统的连接凭据。</span><span class="sxs-lookup"><span data-stu-id="13a10-124">You must also specify connection credentials for the SAP system in the connection URI.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="13a10-125">你可以使用 svcutil.exe 与之前[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，你必须将其配置为使用非默认绑定; 有关如何执行此操作，请参阅[为 SAP 适配器配置 svcutil.exe](#BKMK_ConfigureSvcutil)。</span><span class="sxs-lookup"><span data-stu-id="13a10-125">Before you can use svcutil.exe with the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], you must configure it to use a non-default binding; for information about how to do this, see [Configuring svcutil.exe for the SAP Adapter](#BKMK_ConfigureSvcutil).</span></span>  
  
 <span data-ttu-id="13a10-126">指定在 MEX 终结点和目标操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]连接 URI 按以下方式：</span><span class="sxs-lookup"><span data-stu-id="13a10-126">You specify a MEX endpoint and target operations in the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] connection URI in the following manner:</span></span>  
  
-   <span data-ttu-id="13a10-127">你必须查询字符串中包含"wsdl"参数。</span><span class="sxs-lookup"><span data-stu-id="13a10-127">You must include the "wsdl" parameter in the query string.</span></span> <span data-ttu-id="13a10-128">如果是查询字符串中的第一个参数，其指定为问号 （？） 之后。</span><span class="sxs-lookup"><span data-stu-id="13a10-128">If it is the first parameter in the query string, it is specified just after the question mark (?).</span></span> <span data-ttu-id="13a10-129">如果它不是第一个参数，它应在它前面加一个与号 (&)。</span><span class="sxs-lookup"><span data-stu-id="13a10-129">If it is not the first parameter, it should be preceded with an ampersand (&).</span></span>  
  
-   <span data-ttu-id="13a10-130">你必须执行一个或多个"op"参数"wsdl"的参数。</span><span class="sxs-lookup"><span data-stu-id="13a10-130">You must follow the "wsdl" parameter by one or more "op" parameters.</span></span> <span data-ttu-id="13a10-131">每个"op"参数前面是一个与号 (&)，并指定目标操作的节点 ID。</span><span class="sxs-lookup"><span data-stu-id="13a10-131">Each "op" parameter is preceded by an ampersand (&) and specifies the node ID of a target operation.</span></span>  
  
 <span data-ttu-id="13a10-132">以下三个示例演示如何通过使用 svcutil.exe 来面向各种操作。</span><span class="sxs-lookup"><span data-stu-id="13a10-132">The following three examples show how to target various operations by using svcutil.exe.</span></span>  
  
 <span data-ttu-id="13a10-133">此示例为 RFC_CALCULATE_TAXES 创建 WCF 客户端类。</span><span class="sxs-lookup"><span data-stu-id="13a10-133">This example creates a WCF client class for RFC_CALCULATE_TAXES.</span></span>  
  
 <span data-ttu-id="13a10-134">**.\svcutil "sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?wsdl&op=http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CALCULATE_TAXES"**</span><span class="sxs-lookup"><span data-stu-id="13a10-134">**.\svcutil "sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?wsdl&op=http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CALCULATE_TAXES"**</span></span>  
  
 <span data-ttu-id="13a10-135">此示例创建一个 WCF 客户端类 SALESORDER_CREATEFROMDAT201 和 SALESORDER_CREATEFROMDAT202 IDOC。</span><span class="sxs-lookup"><span data-stu-id="13a10-135">This example creates a WCF client class for both the SALESORDER_CREATEFROMDAT201 and SALESORDER_CREATEFROMDAT202 IDOC.</span></span>  
  
 <span data-ttu-id="13a10-136">**.\svcutil "sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?wsdl&op=http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT201//620/Send&op=http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT202//620/Send"**</span><span class="sxs-lookup"><span data-stu-id="13a10-136">**.\svcutil "sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?wsdl&op=http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT201//620/Send&op=http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT202//620/Send"**</span></span>  
  
 <span data-ttu-id="13a10-137">此示例将创建 WCF 服务约定以 SALESORDER_CREATEFROMDAT201 IDOC 接收 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="13a10-137">This example creates a WCF service contract to receive the SALESORDER_CREATEFROMDAT201 IDOC from the SAP system.</span></span> <span data-ttu-id="13a10-138">节点 ID 指定接收操作。</span><span class="sxs-lookup"><span data-stu-id="13a10-138">The NODE ID specifies a Receive operation.</span></span> <span data-ttu-id="13a10-139">此示例处理检索元数据，因为没有无需连接 URI query_string 中指定的侦听器参数。</span><span class="sxs-lookup"><span data-stu-id="13a10-139">Because this example deals with retrieving metadata, there is no need to specify the listener parameters in the query_string of the connection URI.</span></span>  
  
 <span data-ttu-id="13a10-140">**.\svcutil "sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?wsdl&op=http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT201//620/Receive"**</span><span class="sxs-lookup"><span data-stu-id="13a10-140">**.\svcutil "sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?wsdl&op=http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT201//620/Receive"**</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="13a10-141">必须用引号引起来，在命令行上放置连接 URI。</span><span class="sxs-lookup"><span data-stu-id="13a10-141">You must place the connection URI in quotation marks on the command line.</span></span> <span data-ttu-id="13a10-142">否则，svcutil.exe 会尝试检索操作的元数据，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]不支持。</span><span class="sxs-lookup"><span data-stu-id="13a10-142">Otherwise, svcutil.exe attempts to retrieve metadata for operations that the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] does not support.</span></span> <span data-ttu-id="13a10-143">这类尝试的结果不确定。</span><span class="sxs-lookup"><span data-stu-id="13a10-143">The results of such an attempt are undefined.</span></span>  
  
 <span data-ttu-id="13a10-144">默认情况下，svcutil.exe 将生成的代码文件中的 output.cs;但是，你可以更改输出文件的名称和许多其他选项，svcutil.exe 使用通过设置命令行开关。</span><span class="sxs-lookup"><span data-stu-id="13a10-144">By default, svcutil.exe places the generated code in the output.cs file; however, you can change the name of the output file and many other options that svcutil.exe uses by setting command-line switches.</span></span> <span data-ttu-id="13a10-145">该 svcutil.exe 支持的选项的详细信息，请参阅[ServiceModel 元数据实用工具 (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx)。</span><span class="sxs-lookup"><span data-stu-id="13a10-145">For more information about the options that svcutil.exe supports, see the [ServiceModel Metadata Utility Tool (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx).</span></span>
  
 <span data-ttu-id="13a10-146">Svcutil.exe 不提供的功能 （例如，通过使用通配符） 搜索操作。</span><span class="sxs-lookup"><span data-stu-id="13a10-146">Svcutil.exe does not provide the capability to search for operations (for example, by using wildcard characters).</span></span> <span data-ttu-id="13a10-147">你必须显式指定要设定为目标的特定操作的节点 Id。</span><span class="sxs-lookup"><span data-stu-id="13a10-147">You must explicitly specify node IDs for the specific operations you want to target.</span></span> <span data-ttu-id="13a10-148">等效于其消息的操作字符串运算的节点 ID。</span><span class="sxs-lookup"><span data-stu-id="13a10-148">The node ID of an operation is equivalent to its message action string.</span></span> <span data-ttu-id="13a10-149">不能指定节点仅引用中的类别的 Id。</span><span class="sxs-lookup"><span data-stu-id="13a10-149">You cannot specify node IDs that refer only to categories.</span></span> <span data-ttu-id="13a10-150">有关节点 Id 的详细信息，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]图面，请参阅[元数据的节点 Id](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md)。</span><span class="sxs-lookup"><span data-stu-id="13a10-150">For more information about the node IDs that the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces, see [Metadata Node IDs](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md).</span></span>  
  
 <span data-ttu-id="13a10-151">[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]提供了高级的浏览和搜索功能可以极大地简化生成的 WCF 客户端类和 WCF 服务协定。</span><span class="sxs-lookup"><span data-stu-id="13a10-151">The [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] provides advanced browse and search capabilities that can greatly simplify generating a WCF client class and WCF service contract.</span></span> <span data-ttu-id="13a10-152">有关详细信息[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，请参阅[生成 WCF 客户端或 SAP 解决方案项目关联的 WCF 服务协定](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="13a10-152">For more information about the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], see [Generate a WCF client or a WCF service contract for SAP solution artifacts](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).</span></span>  
  
