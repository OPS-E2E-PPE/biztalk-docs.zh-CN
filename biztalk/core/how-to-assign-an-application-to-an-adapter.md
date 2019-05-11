---
title: 如何向适配器分配应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2ca8850-6789-455b-be53-56f126605c06
caps.latest.revision: 3
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 8e473c10f8e0828389f83293bc7dd219786548c7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342724"
---
# <a name="how-to-assign-an-application-to-an-adapter"></a>如何向适配器分配应用程序
若要处理本地应用程序与远程服务器之间的信息，必须为适配器分配给它的一个或多个应用程序。  
  
### <a name="to-assign-an-application-to-an-adapter"></a>若要为适配器分配应用程序  
  
1.  使用添加到适配器应用程序`ISSOPSAdmin.AssignApplicationToAdapter`。  
  
2.  可以检索分配给一个适配器使用应用程序的当前列表`ISSOAdmin.GetApplicationsForAdapter`。  
  
3.  完成后，您可以通过使用，从适配器删除应用程序`ISSOPSAdmin.RemoveApplicationFromAdapter`。