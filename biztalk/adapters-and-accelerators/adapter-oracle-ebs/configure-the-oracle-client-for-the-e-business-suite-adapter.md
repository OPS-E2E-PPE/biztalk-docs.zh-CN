---
title: 配置 Oracle 客户端 E-business Suite 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 842b6ecc-5334-4cc0-af10-baa7f692ad23
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13c29eef73f5268571c9c9eb33635a0f336954f6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375672"
---
# <a name="configure-the-oracle-client-for-the-e-business-suite-adapter"></a><span data-ttu-id="fd2df-102">配置 Oracle 客户端 E-business Suite 适配器</span><span class="sxs-lookup"><span data-stu-id="fd2df-102">Configure the Oracle client for the E-Business Suite adapter</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="fd2df-103">本主题是只适用于 tnsnames.ora 您用来连接到 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="fd2df-103">This topic is relevant only if you are using tnsnames.ora to connect to the Oracle database.</span></span>  
  
 <span data-ttu-id="fd2df-104">若要建立与[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]，适配器将连接到您的计算机上安装了 Oracle 客户端通过基础的 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="fd2df-104">To establish a connection to the [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)], the adapter connects to the underlying Oracle database through the Oracle client installed on your computer.</span></span> <span data-ttu-id="fd2df-105">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]将 net 服务名称传递到 Oracle 客户端来连接到 Oracle E-business Suite 连接 URI 中指定。</span><span class="sxs-lookup"><span data-stu-id="fd2df-105">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] passes the net service name that you specify in the connection URI to the Oracle client to establish a connection to Oracle E-Business Suite.</span></span> <span data-ttu-id="fd2df-106">网络服务名称是 Oracle 客户端用于获取目标 Oracle 数据库服务的连接信息的别名。</span><span class="sxs-lookup"><span data-stu-id="fd2df-106">The net service name is an alias that the Oracle client uses to acquire connection information for the target Oracle database service.</span></span>  
  
 <span data-ttu-id="fd2df-107">Net 服务名称根据命名方法，它配置为使用 Oracle 客户端解析。</span><span class="sxs-lookup"><span data-stu-id="fd2df-107">The Oracle client resolves the net service name according to the naming method that it is configured to use.</span></span> <span data-ttu-id="fd2df-108">用于 Oracle 网络配置助手配置 Oracle 客户端使用的命名方法。</span><span class="sxs-lookup"><span data-stu-id="fd2df-108">You use the Oracle Net Configuration Assistant to configure the naming methods to be used by the Oracle client.</span></span> <span data-ttu-id="fd2df-109">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]用于连接到 Oracle E-business Suite 支持本地命名方法。</span><span class="sxs-lookup"><span data-stu-id="fd2df-109">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] supports the Local Naming method for connecting to Oracle E-Business Suite.</span></span> <span data-ttu-id="fd2df-110">此方法使用本地文件，tnsnames.ora，net 服务名称解析。</span><span class="sxs-lookup"><span data-stu-id="fd2df-110">This method uses a local file, tnsnames.ora, to resolve the net service name.</span></span>  
  
 <span data-ttu-id="fd2df-111">使用 net 服务名称连接包含的 Oracle 客户端所需的信息来建立与特定的 Oracle 数据库服务 （实例） 的描述符 tnsnames.ora 文件相关联。</span><span class="sxs-lookup"><span data-stu-id="fd2df-111">The tnsnames.ora file associates net service names with connect descriptors that contain the information that the Oracle client needs to establish a connection to a specific Oracle database service (instance).</span></span> <span data-ttu-id="fd2df-112">以下是从 tnsnames.ora 的示例条目。</span><span class="sxs-lookup"><span data-stu-id="fd2df-112">The following is a sample entry from tnsnames.ora.</span></span>  
  
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
  
 <span data-ttu-id="fd2df-113">在此示例条目中，适配器是 net 服务名称。</span><span class="sxs-lookup"><span data-stu-id="fd2df-113">In this sample entry, ADAPTER is the net service name.</span></span> <span data-ttu-id="fd2df-114">连接描述符指定地址信息和与适配器相关联的 Oracle 数据库服务的服务名称。</span><span class="sxs-lookup"><span data-stu-id="fd2df-114">The connect descriptor specifies address information and the service name of the Oracle database service associated with ADAPTER.</span></span> <span data-ttu-id="fd2df-115">您可以使用 Oracle Net Configuration Assistant 来创建和配置 tnsnames.ora 中的 net 服务名称。</span><span class="sxs-lookup"><span data-stu-id="fd2df-115">You can use the Oracle Net Configuration Assistant to create and configure net service names in tnsnames.ora.</span></span> <span data-ttu-id="fd2df-116">配置网络服务名称后，您可以如以下示例所示的连接 URI 中指定它。</span><span class="sxs-lookup"><span data-stu-id="fd2df-116">After you have configured the net service name, you can specify it in a connection URI as in the following example.</span></span>  
  
```  
oracleebs://ADAPTER  
```  
  
 <span data-ttu-id="fd2df-117">有关使用 Oracle Net Configuration Assistant 和 tnsnames.ora 的详细信息，请参阅 Oracle 数据库 Net 服务管理员的指南。</span><span class="sxs-lookup"><span data-stu-id="fd2df-117">For more information about using the Oracle Net Configuration Assistant and about tnsnames.ora, see the Oracle Database Net Services Administrator's Guide.</span></span> <span data-ttu-id="fd2df-118">为特定安装，请咨询数据库管理员有关配置详细信息。</span><span class="sxs-lookup"><span data-stu-id="fd2df-118">Consult your database administrator about configuration details for your specific installation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd2df-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="fd2df-119">See Also</span></span>  
 [<span data-ttu-id="fd2df-120">创建与 Oracle E-business Suite 的连接</span><span class="sxs-lookup"><span data-stu-id="fd2df-120">Create a connection to Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-connection-to-oracle-e-business-suite.md)