---
title: 角色 （服务节点） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Roles node [binding file]
ms.assetid: 847755c9-1697-41a0-b870-f9e795a1a2a6
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ff156bce1fa4114aac34641ce52d28cdf182ecd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65240406"
---
# <a name="roles-service-node"></a><span data-ttu-id="89f27-102">角色 （服务节点）</span><span class="sxs-lookup"><span data-stu-id="89f27-102">Roles (Service Node)</span></span>
<span data-ttu-id="89f27-103">绑定文件的角色节点是所有角色节点，提供有关绑定到与绑定文件一起导出的服务的每个角色的特定信息的父节点。</span><span class="sxs-lookup"><span data-stu-id="89f27-103">The Roles node of a binding file is the parent node for all of the Role nodes which provide specific information about each role bound to a service that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-roles-node"></a><span data-ttu-id="89f27-104">在角色节点中的节点</span><span class="sxs-lookup"><span data-stu-id="89f27-104">Nodes in the Roles node</span></span>  
 <span data-ttu-id="89f27-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="89f27-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="89f27-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="89f27-106">**Name**</span></span>|<span data-ttu-id="89f27-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="89f27-107">**Node Type**</span></span>|<span data-ttu-id="89f27-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="89f27-108">**Data Type**</span></span>|<span data-ttu-id="89f27-109">**说明**</span><span class="sxs-lookup"><span data-stu-id="89f27-109">**Description**</span></span>|<span data-ttu-id="89f27-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="89f27-110">**Restrictions**</span></span>|<span data-ttu-id="89f27-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="89f27-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[<span data-ttu-id="89f27-112">角色</span><span class="sxs-lookup"><span data-stu-id="89f27-112">Role</span></span>](../core/role-roles-node.md)|<span data-ttu-id="89f27-113">录制</span><span class="sxs-lookup"><span data-stu-id="89f27-113">Record</span></span>|<span data-ttu-id="89f27-114">RoleRef (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="89f27-114">RoleRef (ComplexType)</span></span>|<span data-ttu-id="89f27-115">指定有关绑定到与绑定文件一起导出的服务角色信息。</span><span class="sxs-lookup"><span data-stu-id="89f27-115">Specifies information about a role that is bound to a service that is exported with the binding file.</span></span>|<span data-ttu-id="89f27-116">可选</span><span class="sxs-lookup"><span data-stu-id="89f27-116">Not required</span></span>|<span data-ttu-id="89f27-117">默认值：无</span><span class="sxs-lookup"><span data-stu-id="89f27-117">Default value: none</span></span>|