---
title: 架构 Validation1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 599f1bbb-2af5-4278-8b0f-0e5a6517e8e3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35156317c55aa31a0947f244031e1e2b3d2516f6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396881"
---
# <a name="schema-validation"></a><span data-ttu-id="f65d1-102">架构验证</span><span class="sxs-lookup"><span data-stu-id="f65d1-102">Schema Validation</span></span>
<span data-ttu-id="f65d1-103">如果 BizTalk 编辑器扩展提供**ISchemaValidator**对象，该框架将调用**ISchemaValidator.ValidateSchema**当用户调用**验证架构**命令，或在编译时用户生成包含架构的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="f65d1-103">If a BizTalk Editor extension provides an **ISchemaValidator** object, the framework will invoke **ISchemaValidator.ValidateSchema** when the user invokes the **Validate Schema** command, or during compilation when the user builds the BizTalk project containing the schema.</span></span> <span data-ttu-id="f65d1-104">该扩展通常验证的自定义属性，并可以为一个数组中返回的错误消息**IValidationInfo**对象。</span><span class="sxs-lookup"><span data-stu-id="f65d1-104">The extension usually validates the custom properties, and can return error messages as an array of **IValidationInfo** objects.</span></span> <span data-ttu-id="f65d1-105">错误消息显示在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]任务列表窗口中，以及从 BizTalk 编辑器编译器返回的错误。</span><span class="sxs-lookup"><span data-stu-id="f65d1-105">The error messages are displayed in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Task List window, along with errors returned from BizTalk Editor compiler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f65d1-106">请参阅</span><span class="sxs-lookup"><span data-stu-id="f65d1-106">See Also</span></span>  
 [<span data-ttu-id="f65d1-107">扩展 BizTalk 编辑器</span><span class="sxs-lookup"><span data-stu-id="f65d1-107">Extending BizTalk Editor</span></span>](../core/extending-biztalk-editor.md)