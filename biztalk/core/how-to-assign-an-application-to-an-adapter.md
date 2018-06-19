---
title: 如何分配给适配器的应用程序 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f1ea2773-c53c-40a0-a312-015191746451
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf5052d06576988ed71da8458a9d55115fb0b1c8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246669"
---
# <a name="how-to-assign-an-application-to-an-adapter"></a>如何分配给适配器的应用程序
为了处理本地应用程序与远程服务器之间的信息，必须为适配器分配一个或多个应用程序。  
  
### <a name="to-assign-an-application-to-an-adapter"></a>为适配器分配应用程序  
  
1.  使用添加到适配器应用程序`ISSOPSAdmin.AssignApplicationToAdapter`。  
  
2.  你可以检索通过使用分配给适配器的应用程序的当前列表`ISSOAdmin.GetApplicationsForAdapter`。  
  
3.  一旦完成后，你可以通过使用，从适配器删除应用程序`ISSOPSAdmin.RemoveApplicationFromAdapter`。