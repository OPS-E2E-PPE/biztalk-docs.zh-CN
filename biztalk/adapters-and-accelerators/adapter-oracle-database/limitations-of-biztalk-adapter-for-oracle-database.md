---
title: 用于 Oracle 数据库的 BizTalk Adapter 限制 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapter, limitations of
ms.assetid: eab4ddea-f986-43c2-82bb-b9fe37961a5b
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd6cfea523333752c0ee18fefbc6a1848057fe36
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="limitations-of-biztalk-adapter-for-oracle-database"></a><span data-ttu-id="19335-102">用于 Oracle 数据库的 BizTalk Adapter 限制</span><span class="sxs-lookup"><span data-stu-id="19335-102">Limitations of BizTalk Adapter for Oracle Database</span></span>
## <a name="general"></a><span data-ttu-id="19335-103">常规</span><span class="sxs-lookup"><span data-stu-id="19335-103">General</span></span>  
 <span data-ttu-id="19335-104">以下已知的限制[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="19335-104">The following are known limitations for the [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]:</span></span>  
  
-   <span data-ttu-id="19335-105">禁止一些例外情况，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]与以前的版本中的适配器兼容。</span><span class="sxs-lookup"><span data-stu-id="19335-105">Barring some exceptions, the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] is compatible with the previous release of the adapters.</span></span> <span data-ttu-id="19335-106">自最后一个版本以来发生了更改的列表，请参阅[用于 Oracle 数据库的 BizTalk Adapter 中的密钥功能](../../adapters-and-accelerators/adapter-oracle-database/key-features-in-biztalk-adapter-for-oracle-database.md)。</span><span class="sxs-lookup"><span data-stu-id="19335-106">For a list of changes that has happened since the last release, see [Key Features in BizTalk Adapter for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/key-features-in-biztalk-adapter-for-oracle-database.md).</span></span>  
  
-   <span data-ttu-id="19335-107">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不支持 XML 类型。</span><span class="sxs-lookup"><span data-stu-id="19335-107">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not support XML Types.</span></span>  
  
-   <span data-ttu-id="19335-108">SQLEXECUTE 操作不返回扩展值或对过程、 函数或包 IN OUT 参数。</span><span class="sxs-lookup"><span data-stu-id="19335-108">The SQLEXECUTE operation does not return values for OUT or IN OUT parameters to procedures, functions, or packages.</span></span> <span data-ttu-id="19335-109">为此，你必须调用过程、 函数和包使用的专用的操作，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]公开，以便这些 Oracle 项目。</span><span class="sxs-lookup"><span data-stu-id="19335-109">For this reason, you must invoke procedures, functions, and packages by using the dedicated operations that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] exposes for these Oracle artifacts.</span></span>  
  
-   <span data-ttu-id="19335-110">从使用代理编程，Oracle 数据库检索数据时[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不具有多个 65536 节点的 XML 消息反序列化。</span><span class="sxs-lookup"><span data-stu-id="19335-110">When retrieving data from the Oracle database using proxy programming, the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not deserialize XML messages that have more than 65536 nodes.</span></span> <span data-ttu-id="19335-111">请确保响应消息有节点小于或等于为 65536。</span><span class="sxs-lookup"><span data-stu-id="19335-111">Make sure the response message has nodes less than or equal to 65536.</span></span> <span data-ttu-id="19335-112">可以通过修改你的应用程序的 app.config 文件来解决此限制。</span><span class="sxs-lookup"><span data-stu-id="19335-112">You can work around this limitation by modifying the app.config file for your application.</span></span> <span data-ttu-id="19335-113">有关说明，请参阅[排除操作问题与 Oracle 数据库适配器](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-operational-issues-with-the-oracle-database-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="19335-113">For instructions, see [Troubleshoot operational issues with the Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-operational-issues-with-the-oracle-database-adapter.md).</span></span>  
  
-   <span data-ttu-id="19335-114">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]采用输入字符串和构造的适配器，然后执行的 SQL 命令。</span><span class="sxs-lookup"><span data-stu-id="19335-114">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] takes input strings and constructs SQL commands that are then executed by the adapter.</span></span> <span data-ttu-id="19335-115">但是，输入的字符串可能包含其他还会立即执行的 SQL 命令，并且可能会破坏操作协定。</span><span class="sxs-lookup"><span data-stu-id="19335-115">However, the input string might contain other SQL commands that also get executed and might break the operation contract.</span></span>  
  
     <span data-ttu-id="19335-116">请考虑该适配器上提供了对存储过程输入的 REF CURSOR 的方案。</span><span class="sxs-lookup"><span data-stu-id="19335-116">Consider a scenario where the adapter provides an input REF CURSOR to a stored procedure.</span></span> <span data-ttu-id="19335-117">在此类方案中，适配器客户端必须提供命令，在执行时，获取 REF CURSOR。</span><span class="sxs-lookup"><span data-stu-id="19335-117">In such a scenario, the adapter client must provide a command that, when executed, obtains the REF CURSOR.</span></span> <span data-ttu-id="19335-118">适配器，然后在 REF CURSOR 传递给该存储过程。</span><span class="sxs-lookup"><span data-stu-id="19335-118">The adapter then passes on the REF CURSOR to the stored procedure.</span></span> <span data-ttu-id="19335-119">但是，如果用于获取 REF CURSOR 的命令执行一些其他修改数据库时，执行存储的过程的操作协定将断开。</span><span class="sxs-lookup"><span data-stu-id="19335-119">However, if the command for obtaining the REF CURSOR performs some additional modifications to the database, the operation contract for executing the stored procedure is broken.</span></span>  
  
-   <span data-ttu-id="19335-120">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]支持嵌套仅达两个级别的 UDT。</span><span class="sxs-lookup"><span data-stu-id="19335-120">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] supports UDT nesting only up to two levels.</span></span>  
  
-   <span data-ttu-id="19335-121">使用具有适配器时[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，如果在 WCF 自定义的凭据将发送端口不正确，不会处理请求消息。</span><span class="sxs-lookup"><span data-stu-id="19335-121">When using the adapters with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], if the credentials on the WCF-custom send port are incorrect, the request messages are not processed.</span></span> <span data-ttu-id="19335-122">指定正确的凭据后，将消息发送到 Oracle 数据库和收到的响应。</span><span class="sxs-lookup"><span data-stu-id="19335-122">After you specify the correct credentials, the message is sent to the Oracle database and a response is received.</span></span> <span data-ttu-id="19335-123">但是，响应消息不可用到的输出端口。</span><span class="sxs-lookup"><span data-stu-id="19335-123">However, the response message is not available to the out port.</span></span> <span data-ttu-id="19335-124">在这种情况下，你可能需要重新启动主机实例。</span><span class="sxs-lookup"><span data-stu-id="19335-124">In such scenarios, you may need to restart the host instance.</span></span>  
  
-   <span data-ttu-id="19335-125">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不支持复杂类型 （如记录类型，表类型、 UDT 和 VARRAY） 中的 BFILE 数据类型。</span><span class="sxs-lookup"><span data-stu-id="19335-125">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not support the BFILE data type inside complex types (such as RECORD type, TABLE type, UDT, and VARRAY).</span></span>  
  
-   <span data-ttu-id="19335-126">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不支持具有循环引用的用户定义类型 (Udt)。</span><span class="sxs-lookup"><span data-stu-id="19335-126">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not support User-Defined Types (UDTs) that have circular references.</span></span>  
  
-   <span data-ttu-id="19335-127">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不支持包含的字段的记录类型的记录类型的 PL/SQL 表。</span><span class="sxs-lookup"><span data-stu-id="19335-127">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not support records that contain fields of type PL/SQL tables of RECORD type.</span></span>  
  
-   <span data-ttu-id="19335-128">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不会启用客户端设置中为 NULL VARRAY 的第一个元素的值。</span><span class="sxs-lookup"><span data-stu-id="19335-128">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not enable clients to set the value of the first element in a VARRAY to NULL.</span></span>  
  
-   <span data-ttu-id="19335-129">除 PL/SQL 表[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不支持某个包内定义的 Udt。</span><span class="sxs-lookup"><span data-stu-id="19335-129">Except for PL/SQL tables, the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not support UDTs that are defined inside a package.</span></span>  
  
## <a name="limitations-due-to-odpnet"></a><span data-ttu-id="19335-130">由于 ODP.NET 的限制</span><span class="sxs-lookup"><span data-stu-id="19335-130">Limitations due to ODP.NET</span></span>  
 <span data-ttu-id="19335-131">以下已知的限制[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]由于 ODP.NET 的限制：</span><span class="sxs-lookup"><span data-stu-id="19335-131">The following are known limitations for the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] due to the limitation of ODP.NET:</span></span>  
  
-   <span data-ttu-id="19335-132">对于采用十进制值的 Oracle 数据类型，ODP.NET 不引发异常如果输入的值包含字母字符。</span><span class="sxs-lookup"><span data-stu-id="19335-132">For Oracle data types that take decimal values, ODP.NET does not throw an exception if the input value contains alphabetic characters.</span></span> <span data-ttu-id="19335-133">因为[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用与 Oracle 数据库时，适配器 ODP.NET 太不会引发异常时传递字母字符。</span><span class="sxs-lookup"><span data-stu-id="19335-133">Because the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] uses ODP.NET to interface with the Oracle database, the adapter too does not throw an exception when passing alphabetic characters.</span></span> <span data-ttu-id="19335-134">例如：</span><span class="sxs-lookup"><span data-stu-id="19335-134">For example:</span></span>  
  
    -   <span data-ttu-id="19335-135">传递插入操作的值"54r"并不会引发异常;而被插入的值"54"。</span><span class="sxs-lookup"><span data-stu-id="19335-135">Passing a value “54r” for an insert operation does not throw an exception; the value “54” is inserted instead.</span></span>  
  
    -   <span data-ttu-id="19335-136">将值"r54"传递的插入操作不会引发异常;而被插入的值"0"。</span><span class="sxs-lookup"><span data-stu-id="19335-136">Passing a value “r54” for an insert operation does not throw an exception; the value “0” is inserted instead.</span></span>  
  
-   <span data-ttu-id="19335-137">鉴于 ODP.NET 限制，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不支持重载过程使用强类型和弱类型化的 REF CURSOR 的使用。</span><span class="sxs-lookup"><span data-stu-id="19335-137">Because of an ODP.NET limitation, the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not support the use of overloaded procedures using strongly-typed and weakly-typed REF CURSORS.</span></span> <span data-ttu-id="19335-138">在内部，该适配器将这两个强类型和弱类型 REF CURSOR 视为只 REF CURSOR。</span><span class="sxs-lookup"><span data-stu-id="19335-138">Internally, the adapter treats both the strongly-typed and weakly-typed REF CURSORS as just REF CURSORS.</span></span>  
  
-   <span data-ttu-id="19335-139">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不支持 PL/SQL 表按数值字段不编制索引。</span><span class="sxs-lookup"><span data-stu-id="19335-139">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not support PL/SQL tables that are not indexed by a numeric field.</span></span>  
  
-   <span data-ttu-id="19335-140">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不支持不包含任何元素的关联阵列。</span><span class="sxs-lookup"><span data-stu-id="19335-140">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not support associative arrays that do not contain any element.</span></span>  
  
-   <span data-ttu-id="19335-141">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不支持包含使用本地时间区域属性 (TimeStampLTZ) 的时间戳数据类型的 Udt。</span><span class="sxs-lookup"><span data-stu-id="19335-141">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not support UDTs that contain the TimeStamp data type with local time zone attributes (TimeStampLTZ).</span></span>  
  
-   <span data-ttu-id="19335-142">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不支持包含的 Udt"。"</span><span class="sxs-lookup"><span data-stu-id="19335-142">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not support UDTs that contain a “.”</span></span> <span data-ttu-id="19335-143">（句点），在其名称中。</span><span class="sxs-lookup"><span data-stu-id="19335-143">(period) in their names.</span></span>  
  
-   <span data-ttu-id="19335-144">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不支持为 IN OUT 参数中包含 BLOB、 CLOB、 和 NCLOB 数据类型的 Udt。</span><span class="sxs-lookup"><span data-stu-id="19335-144">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not support UDTs that contain BLOB, CLOB, and NCLOB data types as an IN OUT parameter.</span></span>  
  
-   <span data-ttu-id="19335-145">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不支持以下简单类型的 Varray 的 Varray: BFILE、 IntervalDS、 IntervalYM、 TimeStampLTZ 和 TimeStampTZ。</span><span class="sxs-lookup"><span data-stu-id="19335-145">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not support Varray of Varray of the following simple types: BFILE, IntervalDS, IntervalYM, TimeStampLTZ, and TimeStampTZ.</span></span>  
  
-   <span data-ttu-id="19335-146">由于关联的数组的限制，PL/SQL 表或包含任何以下数据类型的记录的 PL/SQL 表中不支持[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="19335-146">Due to the limitation of associative arrays, PL/SQL tables or PL/SQL tables of records that contain any of the following data types are not supported in the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]:</span></span>  
  
    -   <span data-ttu-id="19335-147">BFILE</span><span class="sxs-lookup"><span data-stu-id="19335-147">BFILE</span></span>  
  
    -   <span data-ttu-id="19335-148">BLOB</span><span class="sxs-lookup"><span data-stu-id="19335-148">BLOB</span></span>  
  
    -   <span data-ttu-id="19335-149">CLOB</span><span class="sxs-lookup"><span data-stu-id="19335-149">CLOB</span></span>  
  
    -   <span data-ttu-id="19335-150">IntervalDS</span><span class="sxs-lookup"><span data-stu-id="19335-150">IntervalDS</span></span>  
  
    -   <span data-ttu-id="19335-151">IntervalYM</span><span class="sxs-lookup"><span data-stu-id="19335-151">IntervalYM</span></span>  
  
    -   <span data-ttu-id="19335-152">Long</span><span class="sxs-lookup"><span data-stu-id="19335-152">Long</span></span>  
  
    -   <span data-ttu-id="19335-153">NCLOB</span><span class="sxs-lookup"><span data-stu-id="19335-153">NCLOB</span></span>  
  
    -   <span data-ttu-id="19335-154">RowID</span><span class="sxs-lookup"><span data-stu-id="19335-154">RowID</span></span>  
  
    -   <span data-ttu-id="19335-155">TimeStamp</span><span class="sxs-lookup"><span data-stu-id="19335-155">TimeStamp</span></span>  
  
    -   <span data-ttu-id="19335-156">TimeStampLTZ</span><span class="sxs-lookup"><span data-stu-id="19335-156">TimeStampLTZ</span></span>  
  
    -   <span data-ttu-id="19335-157">TimeStampTZ</span><span class="sxs-lookup"><span data-stu-id="19335-157">TimeStampTZ</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19335-158">另请参阅</span><span class="sxs-lookup"><span data-stu-id="19335-158">See Also</span></span>  
 [<span data-ttu-id="19335-159">了解 BizTalk 适配器用于 Oracle 数据库</span><span class="sxs-lookup"><span data-stu-id="19335-159">Understand the BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/understand-the-biztalk-adapter-for-oracle-database.md)