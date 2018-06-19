---
title: 记录类型的消息架构 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RECORD types, message schemas for
- RECORD types, support for
ms.assetid: 637c42f2-eed0-4941-a6cd-7e03d01088b8
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9022274041e06ad8ccc3f5243715d44d2b64282
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214133"
---
# <a name="message-schemas-for-record-types"></a><span data-ttu-id="4266b-102">记录类型的消息架构</span><span class="sxs-lookup"><span data-stu-id="4266b-102">Message Schemas for RECORD Types</span></span>
<span data-ttu-id="4266b-103">Oracle 记录类型为结构化的 PL/SQL 数据类型组成的一个或更简单或结构化的数据库类型。</span><span class="sxs-lookup"><span data-stu-id="4266b-103">Oracle RECORD types are structured PL/SQL data types that consist of one or more simple or structured database types.</span></span> <span data-ttu-id="4266b-104">记录类型主要用于 PL/SQL 存储过程或函数中来发送和接收层次结构数据。</span><span class="sxs-lookup"><span data-stu-id="4266b-104">RECORD types are primarily used in PL/SQL stored procedures and functions to send and receive hierarchical data.</span></span>  
  
 <span data-ttu-id="4266b-105">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]按以下方式支持记录类型：</span><span class="sxs-lookup"><span data-stu-id="4266b-105">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] supports RECORD types in the following manner:</span></span>  
  
-   <span data-ttu-id="4266b-106">为复杂类型中加以表示记录类型。</span><span class="sxs-lookup"><span data-stu-id="4266b-106">RECORD types are surfaced as complex types.</span></span>  
  
-   <span data-ttu-id="4266b-107">记录类型可以嵌套 （记录在记录中的）。</span><span class="sxs-lookup"><span data-stu-id="4266b-107">RECORD types can be nested (record in a record).</span></span>  
  
-   <span data-ttu-id="4266b-108">记录类型可声明为表中存储的过程和函数的 %rowtype 参数。</span><span class="sxs-lookup"><span data-stu-id="4266b-108">RECORD types can be declared as TABLE%ROWTYPE parameters in stored procedures and functions.</span></span>  
  
-   <span data-ttu-id="4266b-109">记录类型可声明为 PL/SQL 包; 中的类型的记录参数例如， `TYPE rec_type1 IS RECORD(name varchar2(100), age number(3));`。</span><span class="sxs-lookup"><span data-stu-id="4266b-109">RECORD types can be declared as TYPE of RECORD parameters in PL/SQL packages; for example, `TYPE rec_type1 IS RECORD(name varchar2(100), age number(3));`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4266b-110">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不支持作为记录成员 BFILE 类型。</span><span class="sxs-lookup"><span data-stu-id="4266b-110">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not support BFILE types as RECORD members.</span></span>  
  
 <span data-ttu-id="4266b-111">当在存储的过程或函数中使用的记录类型参数时，将使用该操作的命名空间进行限定。</span><span class="sxs-lookup"><span data-stu-id="4266b-111">When a RECORD type parameter is used in a stored procedure or a function, it is qualified with the namespace of that operation.</span></span> <span data-ttu-id="4266b-112">下面的 XML 演示在消息中的记录类型的结构：</span><span class="sxs-lookup"><span data-stu-id="4266b-112">The following XML shows the structure of a RECORD type in a message:</span></span>  
  
```  
<[REC_PARAM_NAME]>  
  <[FIELD_NAME1] xmlns="[OPERATION_NAMESPACE]">value1</[FIELD_NAME1]>  
  <[FIELD_NAME2] xmlns="[OPERATION_NAMESPACE]">value2</[FIELD_NAME2]>  
  …  
</[REC_PARAM_NAME]>  
```  
  
 <span data-ttu-id="4266b-113">[REC_PARAM_NAME] 是记录参数的名称。</span><span class="sxs-lookup"><span data-stu-id="4266b-113">[REC_PARAM_NAME] is the name of the RECORD parameter.</span></span>  
  
 <span data-ttu-id="4266b-114">[字段名] 是字段的中的记录类型的名称。</span><span class="sxs-lookup"><span data-stu-id="4266b-114">[FIELD_NAME] is the name of a field in the RECORD type.</span></span>  
  
 <span data-ttu-id="4266b-115">[OPERATION_NAMESPACE] 是存储的过程或在其中使用的记录参数的函数的命名空间。</span><span class="sxs-lookup"><span data-stu-id="4266b-115">[OPERATION_NAMESPACE] is the namespace of the stored procedure or function in which the RECORD parameter is being used.</span></span>  
  
 <span data-ttu-id="4266b-116">下面的 XML 显示嵌套的记录类型字段的记录类型参数的结构：</span><span class="sxs-lookup"><span data-stu-id="4266b-116">The following XML shows the structure of a RECORD type parameter with a nested RECORD type field:</span></span>  
  
```  
<[REC_PARAM_NAME]>    
  <[FIELD_NAME1] xmlns="[OPERATION_NAMESPACE]">value1</[FIELD_NAME1]>  
  <[FIELD_NAME2] xmlns="[OPERATION_NAMESPACE]">value2</[FIELD_NAME2]>  
  <[REC_PARAM_NAME2]>  
    <[FIELD_NAME1] xmlns="[OPERATION_NAMESPACE]">value1</[FIELD_NAME1]>  
    <[FIELD_NAME2] xmlns="[OPERATION_NAMESPACE]">value1</[FIELD_NAME2]>  
    …  
  </[REC_PARAM_NAME2]>  
  …  
</[REC_PARAM_NAME]>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4266b-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4266b-117">See Also</span></span>  
 [<span data-ttu-id="4266b-118">消息和用于 Oracle 数据库的 BizTalk Adapter 的消息架构</span><span class="sxs-lookup"><span data-stu-id="4266b-118">Messages and Message Schemas for BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)