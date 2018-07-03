---
title: 在 BizTalk Server 中的 Oracle 数据库的 BizTalk 适配器使用 ServiceModel Metadata Utility Tool |Microsoft Docs
description: 使用 svcutil.exe 为非默认绑定，或使用 Oracle DB 适配器的 BizTalk 适配器包 (BAP) 中创建 WCF 客户端类或 WCF 服务协定
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f8660014-da04-4692-89e8-f14fcb419496
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0fe432c9cf7e586269f85beb5f584bbe2aa37210
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999358"
---
# <a name="using-the-servicemodel-metadata-utility-tool-with-the-biztalk-adapter-for-oracle-database"></a><span data-ttu-id="c0f27-103">ServiceModel Metadata Utility Tool 的 BizTalk 适配器将用于 Oracle 数据库</span><span class="sxs-lookup"><span data-stu-id="c0f27-103">Using the ServiceModel Metadata Utility Tool with the BizTalk Adapter for Oracle Database</span></span>
<span data-ttu-id="c0f27-104">可以使用 ServiceModel Metadata Utility Tool (svcutil.exe) 生成 WCF 客户端类或操作的 WCF 服务协定 （接口） 的[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]公开。</span><span class="sxs-lookup"><span data-stu-id="c0f27-104">You can use the ServiceModel Metadata Utility Tool (svcutil.exe) to generate a WCF client class or a WCF service contract (interface) for operations that the [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] exposes.</span></span> <span data-ttu-id="c0f27-105">运行 svcutil.exe 来生成 WCF 客户端类或 WCF 服务协定后，可以在代码中包含生成的文件并创建生成的类的实例也可以实现对 Oracle 执行操作的协定中的 WCF 服务数据库。</span><span class="sxs-lookup"><span data-stu-id="c0f27-105">After you run svcutil.exe to generate either a WCF client class or a WCF service contract, you can include the generated file in your code and create instances of the generated class or implement a WCF service from the contract to perform operations on the Oracle database.</span></span>  
  
 <span data-ttu-id="c0f27-106">使用 svcutil.exe 要求您提供一个连接 URI，其中包含凭据。</span><span class="sxs-lookup"><span data-stu-id="c0f27-106">Using svcutil.exe requires you to supply a connection URI that contains credentials.</span></span> <span data-ttu-id="c0f27-107">因为，默认情况下[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]禁用凭据中的连接 URI，必须配置要使用的非默认绑定的 svcutil.exe [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c0f27-107">Because, by default, the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] disables credentials in the connection URI, you must configure svcutil.exe to use a non-default binding for the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
 <span data-ttu-id="c0f27-108">以下部分介绍如何配置 svcutil.exe 以及如何使用 svcutil.exe 来生成 WCF 客户端代码或具有的 WCF 服务协定[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c0f27-108">The following sections show you how to configure svcutil.exe and how to use svcutil.exe to generate WCF client code or a WCF service contract with the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
##  <a name="BKMK_ConfigureSvcutil"></a> <span data-ttu-id="c0f27-109">配置非默认绑定的 svcutil.exe</span><span class="sxs-lookup"><span data-stu-id="c0f27-109">Configure svcutil.exe for a non-default binding</span></span>   
 <span data-ttu-id="c0f27-110">若要配置 svcutil.exe 使用非默认绑定，您必须创建 svcutil.exe 的本地副本，然后创建或修改 svcutil.exe.config 配置文件的本地副本。</span><span class="sxs-lookup"><span data-stu-id="c0f27-110">To configure svcutil.exe to use a non-default binding, you must create a local copy of svcutil.exe and then create or modify a local copy of the svcutil.exe.config configuration file.</span></span>  
  
1.  <span data-ttu-id="c0f27-111">创建一个文件夹，并将 svcutil.exe 复制到新文件夹。</span><span class="sxs-lookup"><span data-stu-id="c0f27-111">Create a folder, and copy svcutil.exe into the new folder.</span></span> <span data-ttu-id="c0f27-112">通常可以找到 svcutil.exe 在 Windows SDK 安装位置，具体而言，C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin。</span><span class="sxs-lookup"><span data-stu-id="c0f27-112">You can typically find svcutil.exe at the Windows SDK installation location, specifically, C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin.</span></span>  
  
2.  <span data-ttu-id="c0f27-113">创建名为的新文件夹中的 svcutil.exe.config 的文件。</span><span class="sxs-lookup"><span data-stu-id="c0f27-113">Create a file named svcutil.exe.config in the new folder.</span></span>  
  
3.  <span data-ttu-id="c0f27-114">将一个绑定和客户端终结点添加到 svcutil.exe.config 文件。</span><span class="sxs-lookup"><span data-stu-id="c0f27-114">Add a binding and a client endpoint to the svcutil.exe.config file.</span></span> <span data-ttu-id="c0f27-115">您必须从新的文件夹，以确保使用正确的配置运行 svcutil.exe。</span><span class="sxs-lookup"><span data-stu-id="c0f27-115">You must run svcutil.exe from the new folder to ensure that the correct configuration is used.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="c0f27-116">客户端终结点的 name 属性必须指定连接 URI 中使用的方案。</span><span class="sxs-lookup"><span data-stu-id="c0f27-116">The name attribute of the client endpoint must specify the scheme used in the connection URI.</span></span> <span data-ttu-id="c0f27-117">此值区分大小写。</span><span class="sxs-lookup"><span data-stu-id="c0f27-117">This value is case-sensitive.</span></span>  
  
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
>  <span data-ttu-id="c0f27-118">您可以设置的绑定属性的任何[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]绑定配置中。</span><span class="sxs-lookup"><span data-stu-id="c0f27-118">You can set any of the binding properties of the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] in the binding configuration.</span></span>  
  
 <span data-ttu-id="c0f27-119">有关配置 svcutil.exe 的非默认绑定的详细信息，请参阅 WCF 文档中的"自定义安全元数据终结点"主题[ http://go.microsoft.com/fwlink/?LinkId=96077 ](http://go.microsoft.com/fwlink/?LinkId=96077)。</span><span class="sxs-lookup"><span data-stu-id="c0f27-119">For more information about configuring a non-default binding for svcutil.exe, see the "Custom Secure Metadata Endpoint" topic in the WCF documentation at [http://go.microsoft.com/fwlink/?LinkId=96077](http://go.microsoft.com/fwlink/?LinkId=96077).</span></span>  
  
### <a name="configure-a-non-default-binding-for-the-pollingstmt-operation"></a><span data-ttu-id="c0f27-120">配置非默认绑定 POLLINGSTMT 操作</span><span class="sxs-lookup"><span data-stu-id="c0f27-120">Configure a Non-Default Binding for the POLLINGSTMT Operation</span></span>  
 <span data-ttu-id="c0f27-121">若要使用 svcutil.exe 创建 POLLINGSTMT 操作的 WCF 服务协定，必须配置要包括的非默认绑定**pollingStatement**属性，除了**acceptCredentialsInUri**.</span><span class="sxs-lookup"><span data-stu-id="c0f27-121">To use svcutil.exe to create a WCF service contract for the POLLINGSTMT operation, you must configure the non-default binding to include the **pollingStatement** property, in addition to **acceptCredentialsInUri**.</span></span> <span data-ttu-id="c0f27-122">**PollingStatement**必须包含目标表的 SELECT 语句。</span><span class="sxs-lookup"><span data-stu-id="c0f27-122">The **pollingStatement** must contain the SELECT statement that targets the table.</span></span> <span data-ttu-id="c0f27-123">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用此属性以生成类，它表示强类型化结果设置 POLLINGSTMT 操作返回。</span><span class="sxs-lookup"><span data-stu-id="c0f27-123">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] uses this property to generate the class that represents the strongly-typed result set that the POLLINGSTMT operation returns.</span></span> <span data-ttu-id="c0f27-124">下面的示例演示用于生成面向的 POLLINGSTMT 操作的 WCF 服务协定的绑定配置 /SCOTT/EMP 表。</span><span class="sxs-lookup"><span data-stu-id="c0f27-124">The following example shows a binding configuration that is used to generate a WCF service contract for a POLLINGSTMT operation that targets the /SCOTT/EMP table.</span></span>  
  
```  
<bindings>  
    <oracleDBBinding>  
        <binding name="OracleDBBinding" acceptCredentialsInUri="true"   
                                   pollingStatement="SELECT * FROM EMP FOR UPDATE" />  
    </oracleDBBinding>  
</bindings>  
```  
  
## <a name="create-a-wcf-client-class-or-wcf-service-contract-with-svcutilexe"></a><span data-ttu-id="c0f27-125">使用 svcutil.exe 创建 WCF 客户端类或 WCF 服务约定</span><span class="sxs-lookup"><span data-stu-id="c0f27-125">Create a WCF Client Class or WCF Service Contract with svcutil.exe</span></span>  
 <span data-ttu-id="c0f27-126">若要使用 svcutil.exe 为生成 WCF 客户端代码或 WCF 服务协定 （接口） [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，必须提供 URI，指定的 WS-元数据交换 (MEX) 终结点的操作或操作要到 svcutil.exe 的连接生成代码。</span><span class="sxs-lookup"><span data-stu-id="c0f27-126">To use svcutil.exe to generate WCF client code or a WCF service contract (interface) for the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], you must supply a connection URI that specifies an WS-Metadata Exchange (MEX) endpoint and the operation or operations for which you want svcutil.exe to generate code.</span></span> <span data-ttu-id="c0f27-127">此外必须在连接 URI 中指定 Oracle 数据库的连接凭据。</span><span class="sxs-lookup"><span data-stu-id="c0f27-127">You must also specify connection credentials for the Oracle database in the connection URI.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c0f27-128">您可以使用 svcutil.exe 与之前[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，你必须将其配置为使用非默认绑定; 了解有关如何执行此操作，请参阅[Oracle 数据库适配器的配置 svcutil.exe](#BKMK_ConfigureSvcutil)。</span><span class="sxs-lookup"><span data-stu-id="c0f27-128">Before you can use svcutil.exe with the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], you must configure it to use a non-default binding; for information about how to do this, see [Configuring svcutil.exe for the Oracle Database Adapter](#BKMK_ConfigureSvcutil).</span></span>  
  
 <span data-ttu-id="c0f27-129">指定在 MEX 终结点和目标操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]连接 URI 按以下方式：</span><span class="sxs-lookup"><span data-stu-id="c0f27-129">You specify a MEX endpoint and target operations in the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] connection URI in the following manner:</span></span>  
  
- <span data-ttu-id="c0f27-130">你必须在 query_string 中包括"wsdl"参数。</span><span class="sxs-lookup"><span data-stu-id="c0f27-130">You must include the "wsdl" parameter in the query_string.</span></span> <span data-ttu-id="c0f27-131">如果它是 query_string 中的第一个参数，则将其指定之后问号 （？）。</span><span class="sxs-lookup"><span data-stu-id="c0f27-131">If it is the first parameter in the query_string, it is specified just after the question mark (?).</span></span> <span data-ttu-id="c0f27-132">如果它不是第一个参数，它应在前面加上 & 号 (&)。</span><span class="sxs-lookup"><span data-stu-id="c0f27-132">If it is not the first parameter, it should be preceded with an ampersand (&).</span></span>  
  
- <span data-ttu-id="c0f27-133">必须遵循一个或多个"op"参数"wsdl"的参数。</span><span class="sxs-lookup"><span data-stu-id="c0f27-133">You must follow the "wsdl" parameter by one or more "op" parameters.</span></span> <span data-ttu-id="c0f27-134">每个"op"参数的前面有与号 (&)，并指定目标操作的节点 ID。</span><span class="sxs-lookup"><span data-stu-id="c0f27-134">Each "op" parameter is preceded by an ampersand (&) and specifies the node ID of a target operation.</span></span>  
  
  <span data-ttu-id="c0f27-135">以下三个示例演示如何通过使用 svcutil.exe 来面向各种操作。</span><span class="sxs-lookup"><span data-stu-id="c0f27-135">The following three examples show how to target various operations by using svcutil.exe.</span></span>  
  
  <span data-ttu-id="c0f27-136">此示例创建 /SCOTT/EMP 表上插入操作的 WCF 客户端类。</span><span class="sxs-lookup"><span data-stu-id="c0f27-136">This example creates a WCF client class for an Insert operation on the /SCOTT/EMP table.</span></span>  
  
  <span data-ttu-id="c0f27-137">**。 \svcutil"oracledb://User=SCOTT;密码 =TIGER@ADAPTER？ wsdl & op =http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert"**</span><span class="sxs-lookup"><span data-stu-id="c0f27-137">**.\svcutil "oracledb://User=SCOTT;Password=TIGER@ADAPTER?wsdl&op=http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert"**</span></span>  
  
  <span data-ttu-id="c0f27-138">此示例创建一个 WCF 客户端类对于插入和 /SCOTT/EMP 表上的删除操作。</span><span class="sxs-lookup"><span data-stu-id="c0f27-138">This example creates a WCF client class for the Insert and the Delete operations on the /SCOTT/EMP table.</span></span>  
  
  <span data-ttu-id="c0f27-139">**。 \svcutil"oracledb://User=SCOTT;密码 =TIGER@ADAPTER？ wsdl & op =http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert&op=http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Delete"**</span><span class="sxs-lookup"><span data-stu-id="c0f27-139">**.\svcutil "oracledb://User=SCOTT;Password=TIGER@ADAPTER?wsdl&op=http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert&op=http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Delete"**</span></span>  
  
  <span data-ttu-id="c0f27-140">此示例创建 POLLLINGSTMT 操作的 WCF 服务约定。</span><span class="sxs-lookup"><span data-stu-id="c0f27-140">This example creates a WCF service contract for the POLLLINGSTMT operation.</span></span> <span data-ttu-id="c0f27-141">（若要使用 svcutil.exe 生成 POLLINGSTMT 操作的 WCF 服务约定，您必须配置包含一个轮询语句的 svcutil.exe 的非默认绑定。）</span><span class="sxs-lookup"><span data-stu-id="c0f27-141">(To use svcutil.exe to generate a WCF service contract for the POLLINGSTMT operation, you must configure a non-default binding for svcutil.exe that includes a polling statement.)</span></span>  
  
  <span data-ttu-id="c0f27-142">**。 \svcutil"oracledb://User=SCOTT;密码 =TIGER@ADAPTER？ wsdl & op =http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMT"**</span><span class="sxs-lookup"><span data-stu-id="c0f27-142">**.\svcutil "oracledb://User=SCOTT;Password=TIGER@ADAPTER?wsdl&op=http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMT"**</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c0f27-143">必须将连接 URI 放在命令行上的引号。</span><span class="sxs-lookup"><span data-stu-id="c0f27-143">You must place the connection URI in quotation marks on the command line.</span></span> <span data-ttu-id="c0f27-144">否则，svcutil.exe 会尝试检索操作的元数据的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不支持。</span><span class="sxs-lookup"><span data-stu-id="c0f27-144">Otherwise, svcutil.exe attempts to retrieve metadata for operations that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not support.</span></span> <span data-ttu-id="c0f27-145">这类尝试的结果不确定。</span><span class="sxs-lookup"><span data-stu-id="c0f27-145">The results of such an attempt are undefined.</span></span>  
  
 <span data-ttu-id="c0f27-146">默认情况下，svcutil.exe 将生成的代码 output.cs 文件;但是，可以更改输出文件的名称和许多其他选项，svcutil.exe 使用通过设置命令行开关。</span><span class="sxs-lookup"><span data-stu-id="c0f27-146">By default, svcutil.exe places the generated code in the output.cs file; however, you can change the name of the output file and many other options that svcutil.exe uses by setting command-line switches.</span></span> <span data-ttu-id="c0f27-147">该 svcutil.exe 支持的选项的详细信息，请参阅 WCF 文档中的"ServiceModel 元数据实用工具工具 (Svcutil.exe)"主题[ http://go.microsoft.com/fwlink/?LinkId=72777 ](http://go.microsoft.com/fwlink/?LinkId=72777)。</span><span class="sxs-lookup"><span data-stu-id="c0f27-147">For more information about the options that svcutil.exe supports, see the "ServiceModel Metadata Utility Tool (Svcutil.exe)" topic in the WCF documentation at [http://go.microsoft.com/fwlink/?LinkId=72777](http://go.microsoft.com/fwlink/?LinkId=72777).</span></span>  
  
 <span data-ttu-id="c0f27-148">Svcutil.exe 不提供搜索操作 （例如，通过使用通配符） 的功能。</span><span class="sxs-lookup"><span data-stu-id="c0f27-148">Svcutil.exe does not provide the capability to search for operations (for example, by using wildcard characters).</span></span> <span data-ttu-id="c0f27-149">必须显式指定你想要针对的特定操作的节点 Id。</span><span class="sxs-lookup"><span data-stu-id="c0f27-149">You must explicitly specify node IDs for the specific operations you want to target.</span></span> <span data-ttu-id="c0f27-150">不能指定节点只能引用类别的 Id。</span><span class="sxs-lookup"><span data-stu-id="c0f27-150">You cannot specify node IDs that refer only to categories.</span></span> <span data-ttu-id="c0f27-151">详细了解节点 Id 的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]图面，请参阅[元数据节点 Id](../../adapters-and-accelerators/adapter-oracle-database/metadata-node-ids3.md)。</span><span class="sxs-lookup"><span data-stu-id="c0f27-151">For more information about the node IDs that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] surfaces, see [Metadata Node IDs](../../adapters-and-accelerators/adapter-oracle-database/metadata-node-ids3.md).</span></span>  
  
 <span data-ttu-id="c0f27-152">[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]提供高级的浏览和搜索功能，可以极大地简化生成 WCF 客户端类和 WCF 服务约定。</span><span class="sxs-lookup"><span data-stu-id="c0f27-152">The [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] provides advanced browse and search capabilities that can greatly simplify generating a WCF client class and WCF service contract.</span></span> <span data-ttu-id="c0f27-153">有关详细信息[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，请参阅[为 Oracle 数据库解决方案项目生成 WCF 客户端或 WCF 服务约定](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="c0f27-153">For more information about the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], see [Generating a WCF Client or a WCF Service Contract for Oracle Database Solution Artifacts](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0f27-154">请参阅</span><span class="sxs-lookup"><span data-stu-id="c0f27-154">See Also</span></span>  
 [<span data-ttu-id="c0f27-155">Oracle 数据库的 BizTalk 适配器的消息和消息架构</span><span class="sxs-lookup"><span data-stu-id="c0f27-155">Messages and Message Schemas for BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)