---
title: 配置 Oracle 数据库适配器的 Oracle 客户端 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- net service name
- tnsnames.ora
- configuring, the Oracle client
- connect descriptor
- Oracle client, configuring
- Oracle Net Configuration Assistant
- Oracle Net Configuration Assistant, using the
ms.assetid: 2d4c0f20-b3a6-453f-a9b3-65fd5a38c020
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a2186f4ea5400d01f477d0ab98c282e37e32d60
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376699"
---
# <a name="configure-the-oracle-client-for-the-oracle-database-adapter"></a><span data-ttu-id="bdcbd-102">配置 Oracle 数据库适配器的 Oracle 客户端</span><span class="sxs-lookup"><span data-stu-id="bdcbd-102">Configure the Oracle Client for the Oracle Database adapter</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="bdcbd-103">本主题是只适用于 tnsnames.ora 您用来连接到 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="bdcbd-103">This topic is relevant only if you are using tnsnames.ora to connect to the Oracle database.</span></span>  
  
 <span data-ttu-id="bdcbd-104">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]连接到 Oracle 数据库通过您的计算机上安装了 Oracle 客户端。</span><span class="sxs-lookup"><span data-stu-id="bdcbd-104">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] connects to the Oracle database through the Oracle client installed on your computer.</span></span> <span data-ttu-id="bdcbd-105">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]将 net 服务名称传递到 Oracle 客户端来连接到 Oracle 数据库的连接 URI 中指定。</span><span class="sxs-lookup"><span data-stu-id="bdcbd-105">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] passes the net service name that you specify in the connection URI to the Oracle client to establish a connection to the Oracle database.</span></span> <span data-ttu-id="bdcbd-106">网络服务名称是 Oracle 客户端用于获取目标 Oracle 数据库服务的连接信息的别名。</span><span class="sxs-lookup"><span data-stu-id="bdcbd-106">The net service name is an alias that the Oracle client uses to acquire connection information for the target Oracle database service.</span></span>  
  
 <span data-ttu-id="bdcbd-107">Net 服务名称根据命名方法，它配置为使用 Oracle 客户端解析。</span><span class="sxs-lookup"><span data-stu-id="bdcbd-107">The Oracle client resolves the net service name according to the naming method that it is configured to use.</span></span> <span data-ttu-id="bdcbd-108">用于 Oracle 网络配置助手配置 Oracle 客户端使用的命名方法。</span><span class="sxs-lookup"><span data-stu-id="bdcbd-108">You use the Oracle Net Configuration Assistant to configure the naming methods to be used by the Oracle client.</span></span> <span data-ttu-id="bdcbd-109">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]支持用于连接到 Oracle 数据库的本地命名方法。</span><span class="sxs-lookup"><span data-stu-id="bdcbd-109">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] supports the Local Naming method for connecting to the Oracle database.</span></span> <span data-ttu-id="bdcbd-110">此方法使用本地文件，tnsnames.ora，net 服务名称解析。</span><span class="sxs-lookup"><span data-stu-id="bdcbd-110">This method uses a local file, tnsnames.ora, to resolve the net service name.</span></span>  
  
 <span data-ttu-id="bdcbd-111">使用 net 服务名称连接包含 Oracle 客户端来建立与特定的 Oracle 数据库服务 （实例） 建立连接所需的信息的描述符 tnsnames.ora 文件相关联。</span><span class="sxs-lookup"><span data-stu-id="bdcbd-111">The tnsnames.ora file associates net service names with connect descriptors that contain the information the Oracle client needs to establish a connection to a specific Oracle database service (instance).</span></span> <span data-ttu-id="bdcbd-112">以下是从 tnsnames.ora 的示例条目。</span><span class="sxs-lookup"><span data-stu-id="bdcbd-112">The following is a sample entry from tnsnames.ora.</span></span>  
  
```  
ADAPTER =  
  (DESCRIPTION =  
    (ADDRESS_LIST =  
      (ADDRESS = (PROTOCOL = TCP)(HOST = yourOracleServer)(PORT = 1521))  
    )  
    (CONNECT_DATA =  
      (SERVICE_NAME = yourOracleDatabaseServiceName)  
    )  
  )  
```  
  
 <span data-ttu-id="bdcbd-113">在此示例条目中，适配器是 net 服务名称。</span><span class="sxs-lookup"><span data-stu-id="bdcbd-113">In this sample entry, ADAPTER is the net service name.</span></span> <span data-ttu-id="bdcbd-114">连接描述符指定地址信息和与适配器相关联的 Oracle 数据库服务的服务名称。</span><span class="sxs-lookup"><span data-stu-id="bdcbd-114">The connect descriptor specifies address information and the service name of the Oracle database service associated with ADAPTER.</span></span> <span data-ttu-id="bdcbd-115">您可以使用 Oracle Net Configuration Assistant 来创建和配置 tnsnames.ora 中的 net 服务名称。</span><span class="sxs-lookup"><span data-stu-id="bdcbd-115">You can use the Oracle Net Configuration Assistant to create and configure net service names in tnsnames.ora.</span></span> <span data-ttu-id="bdcbd-116">配置网络服务名称后，您可以如以下示例所示的连接 URI 中指定它。</span><span class="sxs-lookup"><span data-stu-id="bdcbd-116">After you have configured the net service name, you can specify it in a connection URI as in the following example.</span></span>  
  
```  
oracledb://ADAPTER  
```  
  
 <span data-ttu-id="bdcbd-117">有关使用 Oracle Net Configuration Assistant 和 tnsnames.ora 的详细信息，请参阅 Oracle 数据库 Net 服务管理员的指南。</span><span class="sxs-lookup"><span data-stu-id="bdcbd-117">For more information about using the Oracle Net Configuration Assistant and about tnsnames.ora, see the Oracle Database Net Services Administrator's Guide.</span></span> <span data-ttu-id="bdcbd-118">为特定安装，请咨询数据库管理员有关配置详细信息。</span><span class="sxs-lookup"><span data-stu-id="bdcbd-118">Consult your database administrator about configuration details for your specific installation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdcbd-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="bdcbd-119">See Also</span></span>  
[<span data-ttu-id="bdcbd-120">创建与 Oracle 数据库的连接</span><span class="sxs-lookup"><span data-stu-id="bdcbd-120">Create a connection to the Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/create-a-connection-to-the-oracle-database.md)