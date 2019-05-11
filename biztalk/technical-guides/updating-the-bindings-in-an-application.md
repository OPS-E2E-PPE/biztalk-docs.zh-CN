---
title: 更新应用程序中的绑定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fe4ee4d8-67bf-4137-94e2-8274107c8ed6
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d92b772665efb2d866c349dd1708d34e022a21b3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65261464"
---
# <a name="updating-the-bindings-in-an-application"></a>更新应用程序中的绑定
更新应用程序中的程序集时，其绑定通常被覆盖，否则该程序集可能未绑定，强制您手动重新配置绑定。 若要避免此问题，可以使用绑定文件更新程序集的相同版本或更新的程序集的较新版本。  
  
## <a name="updating-the-same-version-of-an-assembly"></a>使用相同版本的程序集更新  
 如果程序集具有早期绑定端口或动态端口，并更改 BizTalk Server 管理控制台中的端口配置，设置将会丢失时使用的程序集具有相同的版本号更新程序集。 可以为要更新的程序集导出绑定文件。 在更新后的程序集，可以导入应用程序的程序集，然后导入其绑定文件以重新应用以前的绑定。  
  
## <a name="updating-an-assembly-with-a-newer-version"></a>使用更新的版本更新的程序集  
 可以通过将导出到绑定文件的单个程序集与关联的绑定、 编辑绑定文件以反映新的程序集版本，和然后导入的程序集的绑定，到应用程序更新版本的程序集。 有关编辑绑定文件的详细信息，请参阅[自定义绑定文件](http://go.microsoft.com/fwlink/?LinkID=155000)(超链接"<http://go.microsoft.com/fwlink/?LinkID=155000>" <http://go.microsoft.com/fwlink/?LinkID=155000>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。