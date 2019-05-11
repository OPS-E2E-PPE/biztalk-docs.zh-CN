---
title: 适用于 SQL Server 的 BizTalk 适配器的限制 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5a19b109-a6b7-452f-a544-48627fa52f36
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 582ebdb4bcf41afe0da18d05399650ff56b08789
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368780"
---
# <a name="limitations-of-biztalk-adapter-for-sql-server"></a><span data-ttu-id="d59a0-102">适用于 SQL Server 的 BizTalk 适配器的限制</span><span class="sxs-lookup"><span data-stu-id="d59a0-102">Limitations of BizTalk Adapter for SQL Server</span></span>
<span data-ttu-id="d59a0-103">以下已知的限制[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="d59a0-103">The following are known limitations for [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]:</span></span>  
  
- <span data-ttu-id="d59a0-104">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]不支持在 SQL Server 数据库中创建的同义词。</span><span class="sxs-lookup"><span data-stu-id="d59a0-104">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] does not support synonyms created in the SQL Server database.</span></span> <span data-ttu-id="d59a0-105">有关 SQL Server 中的同义词功能的信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=120111 ](http://go.microsoft.com/fwlink/?LinkId=120111)。</span><span class="sxs-lookup"><span data-stu-id="d59a0-105">For information about synonyms in SQL Server, see [http://go.microsoft.com/fwlink/?LinkId=120111](http://go.microsoft.com/fwlink/?LinkId=120111).</span></span>  
  
- <span data-ttu-id="d59a0-106">如果您更改运行的计算机的系统时间[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]主机，时间不会自动更新中[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]主机。</span><span class="sxs-lookup"><span data-stu-id="d59a0-106">If you change the system time of the computer running the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] host, the time is not updated automatically in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] host.</span></span> <span data-ttu-id="d59a0-107">这可能导致不正确的行为使用的接收端口的入站操作[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d59a0-107">This could lead to incorrect behavior of the inbound operations that use the receive port of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="d59a0-108">解决此问题，必须重新启动主机实例的接收端口后已更改运行它的计算机的系统时间。</span><span class="sxs-lookup"><span data-stu-id="d59a0-108">As a workaround, you must restart the host instance that has a receive port after you have changed the system time of the computer running it.</span></span>  
  
- <span data-ttu-id="d59a0-109">如果在存储过程的参数名称包含 127 或多个字符，则无法执行存储的过程使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d59a0-109">If a parameter name in a stored procedure contains 127 or more characters, you cannot execute the stored procedure using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="d59a0-110">这是因为 ADO.NET 的限制。</span><span class="sxs-lookup"><span data-stu-id="d59a0-110">This is due to the limitation of ADO.NET.</span></span>  
  
- <span data-ttu-id="d59a0-111">WSDL[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]时转换为代理生成、 公开为 System.DateTime DateTimeOffset 列。</span><span class="sxs-lookup"><span data-stu-id="d59a0-111">The WSDL the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] generates, when converted to a proxy, exposes the DateTimeOffset column as System.DateTime.</span></span> <span data-ttu-id="d59a0-112">此数据类型不能存储时区信息。</span><span class="sxs-lookup"><span data-stu-id="d59a0-112">This data type cannot store time zone information.</span></span> <span data-ttu-id="d59a0-113">因此，适配器将发送到代理的任何日期/时间值将转换为.NET 应用程序中的本地时间。</span><span class="sxs-lookup"><span data-stu-id="d59a0-113">As a consequence, any date/time value the adapter sends to the proxy will be converted into local time in the .NET application.</span></span> <span data-ttu-id="d59a0-114">如果您想要保留的时区信息，则必须更改您的代理服务器而不是 System.DateTime 使用字符串类型的接口。</span><span class="sxs-lookup"><span data-stu-id="d59a0-114">If you wish to keep the time zone information, you must change the interface of your proxy to use the String type instead of System.DateTime.</span></span> <span data-ttu-id="d59a0-115">然后，使用 XmlConvert.ToDateTimeOffset 创建 Sytstem.DateTimeOffset 对象，可以存储时区信息。</span><span class="sxs-lookup"><span data-stu-id="d59a0-115">Then, use XmlConvert.ToDateTimeOffset to create a Sytstem.DateTimeOffset object, which can store the timezone information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d59a0-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="d59a0-116">See Also</span></span>  
 [<span data-ttu-id="d59a0-117">了解适用于 SQL Server 的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="d59a0-117">UNderstand BizTalk Adapter for SQL Server</span></span>](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)