---
title: BizTalk Server 中的 Oracle 数据库和 BizTalk 适配器一起使用 ServiceModel 元数据实用工具 |Microsoft 文档
description: 使用 svcutil.exe，对于非默认绑定，或使用 Oracle 数据库适配器-BizTalk 适配器包 (BAP) 中创建的 WCF 客户端类或 WCF 服务协定
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f8660014-da04-4692-89e8-f14fcb419496
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9dfbdbd60333a2e5683b4f37a65edb928a451e46
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
---
# <a name="using-the-servicemodel-metadata-utility-tool-with-the-biztalk-adapter-for-oracle-database"></a><span data-ttu-id="349e2-103">ServiceModel 元数据实用工具使用 BizTalk 适配器将用于 Oracle 数据库</span><span class="sxs-lookup"><span data-stu-id="349e2-103">Using the ServiceModel Metadata Utility Tool with the BizTalk Adapter for Oracle Database</span></span>
<span data-ttu-id="349e2-104">你可以使用 ServiceModel 元数据实用工具 (svcutil.exe) 生成 WCF 客户端类或操作的 WCF 服务协定 （接口），[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]公开。</span><span class="sxs-lookup"><span data-stu-id="349e2-104">You can use the ServiceModel Metadata Utility Tool (svcutil.exe) to generate a WCF client class or a WCF service contract (interface) for operations that the [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] exposes.</span></span> <span data-ttu-id="349e2-105">运行 svcutil.exe 以生成 WCF 客户端类或 WCF 服务协定后，你可以在你的代码中包含生成的文件和创建生成的类的实例或实现从要对 Oracle 执行操作的协定的 WCF 服务数据库。</span><span class="sxs-lookup"><span data-stu-id="349e2-105">After you run svcutil.exe to generate either a WCF client class or a WCF service contract, you can include the generated file in your code and create instances of the generated class or implement a WCF service from the contract to perform operations on the Oracle database.</span></span>  
  
 <span data-ttu-id="349e2-106">使用 svcutil.exe 需要你提供一个连接 URI，其中包含凭据。</span><span class="sxs-lookup"><span data-stu-id="349e2-106">Using svcutil.exe requires you to supply a connection URI that contains credentials.</span></span> <span data-ttu-id="349e2-107">因为，默认情况下，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]禁用凭据在连接 URI，你必须配置要使用的非默认绑定的 svcutil.exe [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="349e2-107">Because, by default, the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] disables credentials in the connection URI, you must configure svcutil.exe to use a non-default binding for the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
 <span data-ttu-id="349e2-108">以下部分说明如何配置 svcutil.exe 以及如何使用 svcutil.exe 生成 WCF 客户端代码或 WCF 服务协定与[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="349e2-108">The following sections show you how to configure svcutil.exe and how to use svcutil.exe to generate WCF client code or a WCF service contract with the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
##  <a name="BKMK_ConfigureSvcutil"></a> <span data-ttu-id="349e2-109">配置非默认绑定的 svcutil.exe</span><span class="sxs-lookup"><span data-stu-id="349e2-109">Configure svcutil.exe for a non-default binding</span></span>   
 <span data-ttu-id="349e2-110">若要配置为使用非默认绑定的 svcutil.exe，你必须创建 svcutil.exe 的本地副本，然后创建或修改 svcutil.exe.config 配置文件的本地副本。</span><span class="sxs-lookup"><span data-stu-id="349e2-110">To configure svcutil.exe to use a non-default binding, you must create a local copy of svcutil.exe and then create or modify a local copy of the svcutil.exe.config configuration file.</span></span>  
  
1.  <span data-ttu-id="349e2-111">创建一个文件夹，并将 svcutil.exe 复制到新文件夹。</span><span class="sxs-lookup"><span data-stu-id="349e2-111">Create a folder, and copy svcutil.exe into the new folder.</span></span> <span data-ttu-id="349e2-112">你通常可以找到 svcutil.exe 在 Windows SDK 安装位置，具体而言，C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin。</span><span class="sxs-lookup"><span data-stu-id="349e2-112">You can typically find svcutil.exe at the Windows SDK installation location, specifically, C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin.</span></span>  
  
2.  <span data-ttu-id="349e2-113">创建名为的新文件夹中的 svcutil.exe.config 的文件。</span><span class="sxs-lookup"><span data-stu-id="349e2-113">Create a file named svcutil.exe.config in the new folder.</span></span>  
  
3.  <span data-ttu-id="349e2-114">将一个绑定和客户端终结点添加到 svcutil.exe.config 文件中。</span><span class="sxs-lookup"><span data-stu-id="349e2-114">Add a binding and a client endpoint to the svcutil.exe.config file.</span></span> <span data-ttu-id="349e2-115">你必须从新的文件夹，以确保使用正确的配置运行 svcutil.exe。</span><span class="sxs-lookup"><span data-stu-id="349e2-115">You must run svcutil.exe from the new folder to ensure that the correct configuration is used.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="349e2-116">客户端终结点的名称属性必须指定连接 URI 中所使用的方案。</span><span class="sxs-lookup"><span data-stu-id="349e2-116">The name attribute of the client endpoint must specify the scheme used in the connection URI.</span></span> <span data-ttu-id="349e2-117">此值区分大小写。</span><span class="sxs-lookup"><span data-stu-id="349e2-117">This value is case-sensitive.</span></span>  
  
    ```  
    <configuration>  
      <system.serviceModel>  
        <client>  
          <!-- the name should match the required scheme of the WS-Metadata Exchange endpoint   
          and the contract should be "IMetadataExchange" -->  
          <endpoint name="oracledb"  
                    binding="oracleDBBinding"  
                    bindingConfiguration="OracleDBBinding"  
                    contract="IMetadataExchange" />  
        </client>  
        <bindings>  
            <oracleDBBinding>  
                <binding name="OracleDBBinding" acceptCredentialsInUri="true" />  
            </oracleDBBinding>  
        </bindings>  
  
      </system.serviceModel>  
  
    </configuration>  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="349e2-118">你可以设置的绑定属性的任何[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]在绑定配置。</span><span class="sxs-lookup"><span data-stu-id="349e2-118">You can set any of the binding properties of the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] in the binding configuration.</span></span>  
  
 <span data-ttu-id="349e2-119">有关配置 svcutil.exe 的非默认绑定的详细信息，请参阅 WCF 文档中的"自定义安全元数据终结点"主题[ http://go.microsoft.com/fwlink/?LinkId=96077 ](http://go.microsoft.com/fwlink/?LinkId=96077)。</span><span class="sxs-lookup"><span data-stu-id="349e2-119">For more information about configuring a non-default binding for svcutil.exe, see the "Custom Secure Metadata Endpoint" topic in the WCF documentation at [http://go.microsoft.com/fwlink/?LinkId=96077](http://go.microsoft.com/fwlink/?LinkId=96077).</span></span>  
  
### <a name="configure-a-non-default-binding-for-the-pollingstmt-operation"></a><span data-ttu-id="349e2-120">配置非默认绑定 POLLINGSTMT 操作</span><span class="sxs-lookup"><span data-stu-id="349e2-120">Configure a Non-Default Binding for the POLLINGSTMT Operation</span></span>  
 <span data-ttu-id="349e2-121">若要使用 svcutil.exe 来创建 WCF 服务协定 POLLINGSTMT 操作，必须配置非默认绑定，以包括**pollingStatement**属性，此外到**acceptCredentialsInUri**.</span><span class="sxs-lookup"><span data-stu-id="349e2-121">To use svcutil.exe to create a WCF service contract for the POLLINGSTMT operation, you must configure the non-default binding to include the **pollingStatement** property, in addition to **acceptCredentialsInUri**.</span></span> <span data-ttu-id="349e2-122">**PollingStatement**必须包含目标表的 SELECT 语句。</span><span class="sxs-lookup"><span data-stu-id="349e2-122">The **pollingStatement** must contain the SELECT statement that targets the table.</span></span> <span data-ttu-id="349e2-123">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用此属性，以生成类，它表示强类型化结果设置 POLLINGSTMT 操作返回。</span><span class="sxs-lookup"><span data-stu-id="349e2-123">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] uses this property to generate the class that represents the strongly-typed result set that the POLLINGSTMT operation returns.</span></span> <span data-ttu-id="349e2-124">下面的示例显示用于生成面向的 POLLINGSTMT 操作的 WCF 服务协定的绑定配置 /SCOTT/EMP 表。</span><span class="sxs-lookup"><span data-stu-id="349e2-124">The following example shows a binding configuration that is used to generate a WCF service contract for a POLLINGSTMT operation that targets the /SCOTT/EMP table.</span></span>  
  
```  
<bindings>  
    <oracleDBBinding>  
        <binding name="OracleDBBinding" acceptCredentialsInUri="true"   
                                   pollingStatement="SELECT * FROM EMP FOR UPDATE" />  
    </oracleDBBinding>  
</bindings>  
```  
  
## <a name="create-a-wcf-client-class-or-wcf-service-contract-with-svcutilexe"></a><span data-ttu-id="349e2-125">使用 svcutil.exe 创建 WCF 客户端类或 WCF 服务协定</span><span class="sxs-lookup"><span data-stu-id="349e2-125">Create a WCF Client Class or WCF Service Contract with svcutil.exe</span></span>  
 <span data-ttu-id="349e2-126">以使用 svcutil.exe 来生成 WCF 客户端代码或 WCF 服务协定 （接口） [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，你必须提供连接 URI，指定 WS 元数据交换 (MEX) 终结点的操作或你想到 svcutil.exe 的操作生成代码。</span><span class="sxs-lookup"><span data-stu-id="349e2-126">To use svcutil.exe to generate WCF client code or a WCF service contract (interface) for the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], you must supply a connection URI that specifies an WS-Metadata Exchange (MEX) endpoint and the operation or operations for which you want svcutil.exe to generate code.</span></span> <span data-ttu-id="349e2-127">你还必须在连接 URI 中指定用于 Oracle 数据库的连接凭据。</span><span class="sxs-lookup"><span data-stu-id="349e2-127">You must also specify connection credentials for the Oracle database in the connection URI.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="349e2-128">你可以使用 svcutil.exe 与之前[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，你必须将其配置为使用非默认绑定; 有关如何执行此操作，请参阅[为 Oracle 数据库适配器配置 svcutil.exe](#BKMK_ConfigureSvcutil)。</span><span class="sxs-lookup"><span data-stu-id="349e2-128">Before you can use svcutil.exe with the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], you must configure it to use a non-default binding; for information about how to do this, see [Configuring svcutil.exe for the Oracle Database Adapter](#BKMK_ConfigureSvcutil).</span></span>  
  
 <span data-ttu-id="349e2-129">指定在 MEX 终结点和目标操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]连接 URI 按以下方式：</span><span class="sxs-lookup"><span data-stu-id="349e2-129">You specify a MEX endpoint and target operations in the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] connection URI in the following manner:</span></span>  
  
-   <span data-ttu-id="349e2-130">你必须在 query_string 中包含"wsdl"参数。</span><span class="sxs-lookup"><span data-stu-id="349e2-130">You must include the "wsdl" parameter in the query_string.</span></span> <span data-ttu-id="349e2-131">如果它是 query_string 中的第一个参数，其指定为问号 （？） 之后。</span><span class="sxs-lookup"><span data-stu-id="349e2-131">If it is the first parameter in the query_string, it is specified just after the question mark (?).</span></span> <span data-ttu-id="349e2-132">如果它不是第一个参数，它应在它前面加一个与号 (&)。</span><span class="sxs-lookup"><span data-stu-id="349e2-132">If it is not the first parameter, it should be preceded with an ampersand (&).</span></span>  
  
-   <span data-ttu-id="349e2-133">你必须执行一个或多个"op"参数"wsdl"的参数。</span><span class="sxs-lookup"><span data-stu-id="349e2-133">You must follow the "wsdl" parameter by one or more "op" parameters.</span></span> <span data-ttu-id="349e2-134">每个"op"参数前面是一个与号 (&)，并指定目标操作的节点 ID。</span><span class="sxs-lookup"><span data-stu-id="349e2-134">Each "op" parameter is preceded by an ampersand (&) and specifies the node ID of a target operation.</span></span>  
  
 <span data-ttu-id="349e2-135">以下三个示例演示如何通过使用 svcutil.exe 来面向各种操作。</span><span class="sxs-lookup"><span data-stu-id="349e2-135">The following three examples show how to target various operations by using svcutil.exe.</span></span>  
  
 <span data-ttu-id="349e2-136">此示例创建 WCF 客户端类上 /SCOTT/EMP 表的插入操作。</span><span class="sxs-lookup"><span data-stu-id="349e2-136">This example creates a WCF client class for an Insert operation on the /SCOTT/EMP table.</span></span>  
  
 <span data-ttu-id="349e2-137">**.\svcutil "oracledb://User=SCOTT;Password=TIGER@ADAPTER?wsdl&op=http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert"**</span><span class="sxs-lookup"><span data-stu-id="349e2-137">**.\svcutil "oracledb://User=SCOTT;Password=TIGER@ADAPTER?wsdl&op=http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert"**</span></span>  
  
 <span data-ttu-id="349e2-138">此示例对插入和删除操作 /SCOTT/EMP 表上的创建一个 WCF 客户端类。</span><span class="sxs-lookup"><span data-stu-id="349e2-138">This example creates a WCF client class for the Insert and the Delete operations on the /SCOTT/EMP table.</span></span>  
  
 <span data-ttu-id="349e2-139">**.\svcutil "oracledb://User=SCOTT;Password=TIGER@ADAPTER?wsdl&op=http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert&op=http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Delete"**</span><span class="sxs-lookup"><span data-stu-id="349e2-139">**.\svcutil "oracledb://User=SCOTT;Password=TIGER@ADAPTER?wsdl&op=http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert&op=http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Delete"**</span></span>  
  
 <span data-ttu-id="349e2-140">此示例创建 POLLLINGSTMT 操作的 WCF 服务协定。</span><span class="sxs-lookup"><span data-stu-id="349e2-140">This example creates a WCF service contract for the POLLLINGSTMT operation.</span></span> <span data-ttu-id="349e2-141">（若要使用 svcutil.exe 生成 WCF 服务协定 POLLINGSTMT 操作，你必须配置一个非默认绑定包含一个轮询的语句的 svcutil.exe。）</span><span class="sxs-lookup"><span data-stu-id="349e2-141">(To use svcutil.exe to generate a WCF service contract for the POLLINGSTMT operation, you must configure a non-default binding for svcutil.exe that includes a polling statement.)</span></span>  
  
 <span data-ttu-id="349e2-142">**.\svcutil "oracledb://User=SCOTT;Password=TIGER@ADAPTER?wsdl&op=http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMT"**</span><span class="sxs-lookup"><span data-stu-id="349e2-142">**.\svcutil "oracledb://User=SCOTT;Password=TIGER@ADAPTER?wsdl&op=http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMT"**</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="349e2-143">必须用引号引起来，在命令行上放置连接 URI。</span><span class="sxs-lookup"><span data-stu-id="349e2-143">You must place the connection URI in quotation marks on the command line.</span></span> <span data-ttu-id="349e2-144">否则，svcutil.exe 会尝试检索操作的元数据，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不支持。</span><span class="sxs-lookup"><span data-stu-id="349e2-144">Otherwise, svcutil.exe attempts to retrieve metadata for operations that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not support.</span></span> <span data-ttu-id="349e2-145">这类尝试的结果不确定。</span><span class="sxs-lookup"><span data-stu-id="349e2-145">The results of such an attempt are undefined.</span></span>  
  
 <span data-ttu-id="349e2-146">默认情况下，svcutil.exe 将生成的代码文件中的 output.cs;但是，你可以更改输出文件的名称和许多其他选项，svcutil.exe 使用通过设置命令行开关。</span><span class="sxs-lookup"><span data-stu-id="349e2-146">By default, svcutil.exe places the generated code in the output.cs file; however, you can change the name of the output file and many other options that svcutil.exe uses by setting command-line switches.</span></span> <span data-ttu-id="349e2-147">该 svcutil.exe 支持的选项的详细信息，请参阅 WCF 文档中的"ServiceModel 元数据实用工具 (Svcutil.exe)"主题[ http://go.microsoft.com/fwlink/?LinkId=72777 ](http://go.microsoft.com/fwlink/?LinkId=72777)。</span><span class="sxs-lookup"><span data-stu-id="349e2-147">For more information about the options that svcutil.exe supports, see the "ServiceModel Metadata Utility Tool (Svcutil.exe)" topic in the WCF documentation at [http://go.microsoft.com/fwlink/?LinkId=72777](http://go.microsoft.com/fwlink/?LinkId=72777).</span></span>  
  
 <span data-ttu-id="349e2-148">Svcutil.exe 不提供的功能 （例如，通过使用通配符） 搜索操作。</span><span class="sxs-lookup"><span data-stu-id="349e2-148">Svcutil.exe does not provide the capability to search for operations (for example, by using wildcard characters).</span></span> <span data-ttu-id="349e2-149">你必须显式指定要设定为目标的特定操作的节点 Id。</span><span class="sxs-lookup"><span data-stu-id="349e2-149">You must explicitly specify node IDs for the specific operations you want to target.</span></span> <span data-ttu-id="349e2-150">不能指定节点仅引用中的类别的 Id。</span><span class="sxs-lookup"><span data-stu-id="349e2-150">You cannot specify node IDs that refer only to categories.</span></span> <span data-ttu-id="349e2-151">有关节点 Id 的详细信息，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]图面，请参阅[元数据的节点 Id](../../adapters-and-accelerators/adapter-oracle-database/metadata-node-ids3.md)。</span><span class="sxs-lookup"><span data-stu-id="349e2-151">For more information about the node IDs that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] surfaces, see [Metadata Node IDs](../../adapters-and-accelerators/adapter-oracle-database/metadata-node-ids3.md).</span></span>  
  
 <span data-ttu-id="349e2-152">[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]提供了高级的浏览和搜索功能可以极大地简化生成的 WCF 客户端类和 WCF 服务协定。</span><span class="sxs-lookup"><span data-stu-id="349e2-152">The [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] provides advanced browse and search capabilities that can greatly simplify generating a WCF client class and WCF service contract.</span></span> <span data-ttu-id="349e2-153">有关详细信息[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，请参阅[生成的 Oracle 数据库解决方案项目 WCF 客户端或 WCF 服务约定](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="349e2-153">For more information about the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], see [Generating a WCF Client or a WCF Service Contract for Oracle Database Solution Artifacts](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="349e2-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="349e2-154">See Also</span></span>  
 [<span data-ttu-id="349e2-155">Oracle 数据库的 BizTalk 适配器的消息和消息架构</span><span class="sxs-lookup"><span data-stu-id="349e2-155">Messages and Message Schemas for BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)