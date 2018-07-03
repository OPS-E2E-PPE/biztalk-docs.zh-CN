---
title: 对函数和过程的 Oracle 数据库中的记录类型的操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RECORD type
ms.assetid: 28ecb76c-de82-43df-83cc-917c482417b3
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2635ac4b21173fe1a12603c60263dfa70b5a18e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974198"
---
# <a name="operations-on-functions-and-procedures-with-record-types-in-oracle-database"></a><span data-ttu-id="2a475-102">对函数和过程的 Oracle 数据库中的记录类型的操作</span><span class="sxs-lookup"><span data-stu-id="2a475-102">Operations on Functions and Procedures with RECORD Types in Oracle Database</span></span>
<span data-ttu-id="2a475-103">Oracle 记录类型用于表示层次结构中传递到 PL/SQL 函数和过程的参数信息。</span><span class="sxs-lookup"><span data-stu-id="2a475-103">Oracle RECORD types are used to represent hierarchical information in parameters passed to PL/SQL functions and procedures.</span></span> <span data-ttu-id="2a475-104">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]呈现为 XML 的复杂类型的记录类型。</span><span class="sxs-lookup"><span data-stu-id="2a475-104">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] surfaces RECORD types as complex XML types.</span></span> <span data-ttu-id="2a475-105">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]支持以下类型的记录类型：</span><span class="sxs-lookup"><span data-stu-id="2a475-105">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] supports the following kinds of RECORD types:</span></span>  
  
- <span data-ttu-id="2a475-106">声明为表 %行类型参数在存储的过程和函数中的记录类型。</span><span class="sxs-lookup"><span data-stu-id="2a475-106">RECORD types that are declared as TABLE%ROWTYPE parameters in stored procedures and functions.</span></span>  
  
- <span data-ttu-id="2a475-107">例如，声明为类型的记录参数 PL/SQL 包中的记录类型键入 rec_type1 是 RECORD(name varchar2(100), age number(3));</span><span class="sxs-lookup"><span data-stu-id="2a475-107">RECORD types that are declared as TYPE of RECORD parameters in PL/SQL packages for example, TYPE rec_type1 IS RECORD(name varchar2(100), age number(3));</span></span>  
  
- <span data-ttu-id="2a475-108">包含嵌套的记录的记录类型。</span><span class="sxs-lookup"><span data-stu-id="2a475-108">RECORD types that contain nested records.</span></span>  
  
- <span data-ttu-id="2a475-109">缩小，显示作为中的记录类型或为过程或函数在 OUT 参数。</span><span class="sxs-lookup"><span data-stu-id="2a475-109">RECORD types that appear as IN, OUT, or IN OUT parameters to procedures or functions.</span></span>  
  
- <span data-ttu-id="2a475-110">是函数的返回值的记录类型。</span><span class="sxs-lookup"><span data-stu-id="2a475-110">RECORD types that are RETURN values of functions.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="2a475-111">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不支持 BFILE 作为记录成员的类型。</span><span class="sxs-lookup"><span data-stu-id="2a475-111">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not support BFILE types as RECORD members.</span></span>  
  
  <span data-ttu-id="2a475-112">有关信息：</span><span class="sxs-lookup"><span data-stu-id="2a475-112">For information about:</span></span>  
  
- <span data-ttu-id="2a475-113">调用的函数或过程涉及使用 WCF 服务模型的记录类型，请参阅[运行操作使用记录的类型在 Oracle 数据库中使用 WCF 服务模型](../../adapters-and-accelerators/adapter-oracle-database/using-record-types-in-oracle-database-using-the-wcf-service-model.md)。</span><span class="sxs-lookup"><span data-stu-id="2a475-113">Invoking a function or procedure involving RECORD types using the WCF service model, see [Run Operations Using RECORD Types in Oracle Database using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/using-record-types-in-oracle-database-using-the-wcf-service-model.md).</span></span>  
  
- <span data-ttu-id="2a475-114">调用的函数或过程涉及记录类型使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[调用的函数和过程的记录类型通过使用 BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-functions-and-procedures-with-record-types-in-oracle-db-with-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="2a475-114">Invoking a function or procedure involving RECORD types using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], see [Invoke Functions and Procedures with RECORD Types by Using BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-functions-and-procedures-with-record-types-in-oracle-db-with-biztalk-server.md).</span></span>  
  
- <span data-ttu-id="2a475-115">记录的 XML 结构类型所支持的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[记录类型的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-record-types.md)。</span><span class="sxs-lookup"><span data-stu-id="2a475-115">XML structure for RECORD types as supported by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Message Schemas for RECORD Types](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-record-types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a475-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="2a475-116">See Also</span></span>  
 <span data-ttu-id="2a475-117">[哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="2a475-117">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>