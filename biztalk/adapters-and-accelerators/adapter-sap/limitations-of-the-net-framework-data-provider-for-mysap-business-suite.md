---
title: 用于 mySAP Business Suite 的.NET Framework 数据提供程序的限制 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Data Provider for SAP, limitations of
- .NET Framework Data Provider for mySAP Business Suite, limitations of
ms.assetid: 462e627d-41da-4456-bc62-e8cf7296f5b4
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9efcf7fb18471c92c504e08df43482fbc64064d2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999814"
---
# <a name="limitations-of-the-net-framework-data-provider-for-mysap-business-suite"></a><span data-ttu-id="281a7-102">.NET Framework Data Provider for mySAP Business Suite 的限制</span><span class="sxs-lookup"><span data-stu-id="281a7-102">Limitations of the .NET Framework Data Provider for mySAP Business Suite</span></span>
<span data-ttu-id="281a7-103">以下已知的限制[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]):</span><span class="sxs-lookup"><span data-stu-id="281a7-103">The following are known limitations of the [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]):</span></span>  
  
- <span data-ttu-id="281a7-104">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]不支持连接到 SAP 系统使用安全网络连接 (SNC)。</span><span class="sxs-lookup"><span data-stu-id="281a7-104">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] does not support connecting to an SAP system using Secure Network Connection (SNC).</span></span> <span data-ttu-id="281a7-105">SNC 有关详细信息，请参阅[SAP 系统和适配器之间的安全](../../adapters-and-accelerators/adapter-sap/security-between-the-sap-system-and-the-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="281a7-105">For more information about SNC, see [Security between the SAP system and the adapter](../../adapters-and-accelerators/adapter-sap/security-between-the-sap-system-and-the-adapter.md).</span></span>
  
- <span data-ttu-id="281a7-106">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]不支持`DbType`或`Size`的属性`SAPParameter`。</span><span class="sxs-lookup"><span data-stu-id="281a7-106">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] does not support the `DbType` or `Size` properties of the `SAPParameter`.</span></span> <span data-ttu-id="281a7-107">相反，当用户指定的值`SAPParameter`，值在内部强制转换为根据.NET 和 SAP 数据类型之间已建立的映射的.NET 数据类型。</span><span class="sxs-lookup"><span data-stu-id="281a7-107">Instead, when the user specifies a value for the `SAPParameter`, the value is cast internally to a .NET data type according to the established mapping between .NET and SAP data types.</span></span>  
  
- <span data-ttu-id="281a7-108">为 SAP 数据类型的字段值允许的最大长度`CURR`， `DEC`，和`QUAN`是 29 位数字。</span><span class="sxs-lookup"><span data-stu-id="281a7-108">The maximum length allowed for field values of SAP data types `CURR`, `DEC`, and `QUAN` is 29 digits.</span></span> <span data-ttu-id="281a7-109">虽然 SAP 以本机方式提供这些数据类型值的 31 位置，但.NET decimal 数据类型转换为实施 29 位数字限制。</span><span class="sxs-lookup"><span data-stu-id="281a7-109">Although SAP provides 31 places for these data-type values natively, the .NET decimal data type to which they are converted imposes a 29-digit limit.</span></span>  
  
- <span data-ttu-id="281a7-110">.NET 数据类型之间的映射限制`Double`和 SAP `FLTP` SAP 系统中的数据读入的.NET 类型时，数据类型可能会导致溢出错误。</span><span class="sxs-lookup"><span data-stu-id="281a7-110">A mapping limitation between the .NET data type `Double` and the SAP `FLTP` data type can cause an overflow error when reading data from the SAP system into the .NET type.</span></span> <span data-ttu-id="281a7-111">尽管.NET 类型可以表示双精度 64 位数字，其值范围从-1.79769313486232e308 到正 1.79769313486232 e 308，SAP`FLTP`类型分析[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]不能超过 1.8446744073709552E + 19;有效的限制`FLTP`类型是负 1.8446744073709552E + 正 1.8446744073709552E + 19 到 19 的范围。</span><span class="sxs-lookup"><span data-stu-id="281a7-111">Although the .NET type can represent a double-precision 64-bit number with values ranging from negative 1.79769313486232e308 to positive 1.79769313486232e308, an SAP `FLTP` type parsed by the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] cannot exceed 1.8446744073709552E+19; the effective limit for the `FLTP` type is the range negative 1.8446744073709552E+19 to positive 1.8446744073709552E+19.</span></span>  
  
- <span data-ttu-id="281a7-112">由于基础客户端库，超时处理问题[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]不支持命令，并连接超时。</span><span class="sxs-lookup"><span data-stu-id="281a7-112">Due to issues with timeout handling by the underlying client library, the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] does not support command and connection timeout.</span></span>  
  
- <span data-ttu-id="281a7-113">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]不支持异步命令的行为。</span><span class="sxs-lookup"><span data-stu-id="281a7-113">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] does not support asynchronous command behavior.</span></span>  
  
- <span data-ttu-id="281a7-114">当使用 SQL Server Integration Services (SSIS) 项目，使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]无法检索包含超过 8000 个字符的值的列的数据。</span><span class="sxs-lookup"><span data-stu-id="281a7-114">When used with a SQL Server Integration Services (SSIS) project, the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] fails to retrieve data for columns that contain values with more than 8000 characters.</span></span> <span data-ttu-id="281a7-115">这是因为依据的 SSIS 限制：</span><span class="sxs-lookup"><span data-stu-id="281a7-115">This is due to an SSIS restriction according to which:</span></span>  
  
  -   <span data-ttu-id="281a7-116">不支持大于 4000 个字符中的 SSIS 变量的值。</span><span class="sxs-lookup"><span data-stu-id="281a7-116">Values greater than 4000 characters in SSIS variable are not supported.</span></span>  
  
  -   <span data-ttu-id="281a7-117">不支持大于 4000 个宽字符的值。</span><span class="sxs-lookup"><span data-stu-id="281a7-117">Values greater than 4000 wide characters are not supported.</span></span>  
  
  -   <span data-ttu-id="281a7-118">不支持大于 8000 的单字节字符的值。</span><span class="sxs-lookup"><span data-stu-id="281a7-118">Values greater than 8000 single-byte characters are not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="281a7-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="281a7-119">See Also</span></span>  
 [<span data-ttu-id="281a7-120">关于 mySAP Business Suite 的 .NET Framework 数据提供程序</span><span class="sxs-lookup"><span data-stu-id="281a7-120">About the .NET Framework Data Provider for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)