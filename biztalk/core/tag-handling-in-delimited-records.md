---
title: 标记分隔记录中的处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 568eb804-bea5-46d4-8547-8bc30b87156c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c50a3daad9bb77ba4a9cbc264f018e29601edfff
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972462"
---
# <a name="tag-handling-in-delimited-records"></a><span data-ttu-id="edf5b-102">分隔记录中的标记处理</span><span class="sxs-lookup"><span data-stu-id="edf5b-102">Tag Handling in Delimited Records</span></span>

## <a name="overview"></a><span data-ttu-id="edf5b-103">概述</span><span class="sxs-lookup"><span data-stu-id="edf5b-103">Overview</span></span>
<span data-ttu-id="edf5b-104">分隔的记录可以包含的已知字符序列，称为一个标记，它可用于消除从另一个记录的一种类型的歧义。</span><span class="sxs-lookup"><span data-stu-id="edf5b-104">Delimited records can include a well-known sequence of characters, known as a tag, which can be used to disambiguate one type of record from another.</span></span> <span data-ttu-id="edf5b-105">这样，平面文件拆装器以便正确标识适当**记录**中包含正确解析平面文件记录所需的信息的架构的节点。</span><span class="sxs-lookup"><span data-stu-id="edf5b-105">This will allow the flat file disassembler to properly identify the appropriate **Record** node in the schema that contains the information required to correctly parse the flat file record.</span></span>  

 <span data-ttu-id="edf5b-106">可以使用**标记标识符**属性可指定分隔记录中的标记。</span><span class="sxs-lookup"><span data-stu-id="edf5b-106">You can use the **Tag Identifier** property to specify the tag within a delimited record.</span></span> <span data-ttu-id="edf5b-107">与不同的位置记录中的标记，分隔记录中的标记必须出现在分隔记录的开头，并记录转换为其等效的 XML 格式时永远不会自动包含在数据。</span><span class="sxs-lookup"><span data-stu-id="edf5b-107">Unlike tags in positional records, tags in delimited records must occur at the beginning of the delimited record and are automatically never included in the data when the record is translated to its equivalent XML format.</span></span>  

## <a name="see-also"></a><span data-ttu-id="edf5b-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="edf5b-108">See Also</span></span>  
- [<span data-ttu-id="edf5b-109">分隔记录注意事项</span><span class="sxs-lookup"><span data-stu-id="edf5b-109">Delimited Record Considerations</span></span>](../core/delimited-record-considerations.md)   
- <span data-ttu-id="edf5b-110">**标记标识符 （平面文件架构的节点属性）** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="edf5b-110">**Tag Identifier (Node Property of Flat File Schemas)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
