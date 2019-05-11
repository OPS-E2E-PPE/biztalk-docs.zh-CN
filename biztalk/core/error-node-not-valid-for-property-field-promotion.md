---
title: 错误-节点不适于属性字段升级 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.nodeNotValidForPropFieldProm
ms.assetid: ee386309-d134-4e5f-b9fe-f7cb6cca2819
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc079c9668ecdb5a85423047c6706b2656e5fbf4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388530"
---
# <a name="error---node-not-valid-for-property-field-promotion"></a><span data-ttu-id="7442c-102">错误-节点不适于属性字段升级</span><span class="sxs-lookup"><span data-stu-id="7442c-102">Error - Node Not Valid For Property Field Promotion</span></span>
<span data-ttu-id="7442c-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="7442c-103">**Error Code**</span></span>  
  
 <span data-ttu-id="7442c-104">BEC2001</span><span class="sxs-lookup"><span data-stu-id="7442c-104">BEC2001</span></span>  
  
 <span data-ttu-id="7442c-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="7442c-105">**Explanation**</span></span>  
  
 <span data-ttu-id="7442c-106">不能作为属性字段升级所指示的节点，因为它不能包含必需的文本内容。</span><span class="sxs-lookup"><span data-stu-id="7442c-106">The indicated node cannot be promoted as a Property Field because it cannot contain the required text content.</span></span> <span data-ttu-id="7442c-107">仅**Field 元素**节点， **Field 特性**节点，或**记录**具有混合内容或简单内容的节点可以升级为属性字段。</span><span class="sxs-lookup"><span data-stu-id="7442c-107">Only **Field Element** nodes, **Field Attribute** nodes, or **Record** nodes with mixed or simple content can be promoted as Property Fields.</span></span>  
  
 <span data-ttu-id="7442c-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="7442c-108">**User Action**</span></span>  
  
 <span data-ttu-id="7442c-109">使用**属性字段**选项卡**升级属性**对话框删除禁止使用的属性升级。</span><span class="sxs-lookup"><span data-stu-id="7442c-109">Use the **Property Fields** tab in the **Promote Properties** dialog box to remove the disallowed property promotion.</span></span>