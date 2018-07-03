---
title: 消息架构的记录类型 |Microsoft Docs
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
ms.openlocfilehash: aae82fad713fd9a2789e165845958421e1213402
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996918"
---
# <a name="message-schemas-for-record-types"></a><span data-ttu-id="d32ef-102">记录类型的消息架构</span><span class="sxs-lookup"><span data-stu-id="d32ef-102">Message Schemas for RECORD Types</span></span>
<span data-ttu-id="d32ef-103">Oracle 记录类型是结构化的 PL/SQL 数据类型组成的一个或更简单或结构化的数据库类型。</span><span class="sxs-lookup"><span data-stu-id="d32ef-103">Oracle RECORD types are structured PL/SQL data types that consist of one or more simple or structured database types.</span></span> <span data-ttu-id="d32ef-104">记录类型主要用于在 PL/SQL 存储过程和函数来发送和接收分层数据。</span><span class="sxs-lookup"><span data-stu-id="d32ef-104">RECORD types are primarily used in PL/SQL stored procedures and functions to send and receive hierarchical data.</span></span>  
  
 <span data-ttu-id="d32ef-105">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]按以下方式支持记录类型：</span><span class="sxs-lookup"><span data-stu-id="d32ef-105">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] supports RECORD types in the following manner:</span></span>  
  
- <span data-ttu-id="d32ef-106">记录类型显示为复杂类型。</span><span class="sxs-lookup"><span data-stu-id="d32ef-106">RECORD types are surfaced as complex types.</span></span>  
  
- <span data-ttu-id="d32ef-107">记录类型可以是嵌套 （记录在记录中的）。</span><span class="sxs-lookup"><span data-stu-id="d32ef-107">RECORD types can be nested (record in a record).</span></span>  
  
- <span data-ttu-id="d32ef-108">记录类型可以声明为表 %行类型参数在存储的过程和函数。</span><span class="sxs-lookup"><span data-stu-id="d32ef-108">RECORD types can be declared as TABLE%ROWTYPE parameters in stored procedures and functions.</span></span>  
  
- <span data-ttu-id="d32ef-109">记录类型可以声明为 PL/SQL 包; 中的类型的记录参数例如， `TYPE rec_type1 IS RECORD(name varchar2(100), age number(3));`。</span><span class="sxs-lookup"><span data-stu-id="d32ef-109">RECORD types can be declared as TYPE of RECORD parameters in PL/SQL packages; for example, `TYPE rec_type1 IS RECORD(name varchar2(100), age number(3));`.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="d32ef-110">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不支持 BFILE 作为记录成员的类型。</span><span class="sxs-lookup"><span data-stu-id="d32ef-110">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not support BFILE types as RECORD members.</span></span>  
  
  <span data-ttu-id="d32ef-111">存储的过程或函数中使用的记录类型参数时，将使用该操作的命名空间进行限定。</span><span class="sxs-lookup"><span data-stu-id="d32ef-111">When a RECORD type parameter is used in a stored procedure or a function, it is qualified with the namespace of that operation.</span></span> <span data-ttu-id="d32ef-112">下面的 XML 演示在消息中的记录类型的结构：</span><span class="sxs-lookup"><span data-stu-id="d32ef-112">The following XML shows the structure of a RECORD type in a message:</span></span>  
  
```  
<[REC_PARAM_NAME]>  
  <[FIELD_NAME1] xmlns="[OPERATION_NAMESPACE]">value1</[FIELD_NAME1]>  
  <[FIELD_NAME2] xmlns="[OPERATION_NAMESPACE]">value2</[FIELD_NAME2]>  
  …  
</[REC_PARAM_NAME]>  
```  
  
 <span data-ttu-id="d32ef-113">[REC_PARAM_NAME] 是记录参数的名称。</span><span class="sxs-lookup"><span data-stu-id="d32ef-113">[REC_PARAM_NAME] is the name of the RECORD parameter.</span></span>  
  
 <span data-ttu-id="d32ef-114">[字段名] 是字段的记录类型中的名称。</span><span class="sxs-lookup"><span data-stu-id="d32ef-114">[FIELD_NAME] is the name of a field in the RECORD type.</span></span>  
  
 <span data-ttu-id="d32ef-115">[OPERATION_NAMESPACE] 是存储的过程或函数的记录参数在其中使用的命名空间。</span><span class="sxs-lookup"><span data-stu-id="d32ef-115">[OPERATION_NAMESPACE] is the namespace of the stored procedure or function in which the RECORD parameter is being used.</span></span>  
  
 <span data-ttu-id="d32ef-116">以下 XML 显示了具有嵌套的记录类型字段的记录类型参数的结构：</span><span class="sxs-lookup"><span data-stu-id="d32ef-116">The following XML shows the structure of a RECORD type parameter with a nested RECORD type field:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d32ef-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="d32ef-117">See Also</span></span>  
 [<span data-ttu-id="d32ef-118">Oracle 数据库的 BizTalk 适配器的消息和消息架构</span><span class="sxs-lookup"><span data-stu-id="d32ef-118">Messages and Message Schemas for BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)