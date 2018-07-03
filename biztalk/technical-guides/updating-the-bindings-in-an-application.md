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
ms.openlocfilehash: 0add0638196e992f74ab53ebda7c429c97ca3aab
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996558"
---
# <a name="updating-the-bindings-in-an-application"></a>更新应用程序中的绑定
在更新应用程序中的一个程序集时，通常会覆盖该程序集的绑定，也有可能该程序集根本未绑定，所以您不得不手动重新配置绑定。 若要避免此问题，可以使用绑定文件更新程序集的相同版本或更新的程序集的较新版本。  
  
## <a name="updating-the-same-version-of-an-assembly"></a>使用相同版本的程序集更新  
 如果程序集具有早期绑定端口或动态端口，而您在 BizTalk Server 管理控制台中更改了端口配置，在您使用相同版本号的程序集来更新当前程序集时这些设置将丢失。 可以为要更新的程序集导出绑定文件。 在更新后的程序集，可以导入应用程序的程序集，然后导入其绑定文件以重新应用以前的绑定。  
  
## <a name="updating-an-assembly-with-a-newer-version"></a>使用更新的版本更新的程序集  
 可以通过将导出到绑定文件的单个程序集与关联的绑定、 编辑绑定文件以反映新的程序集版本，和然后导入的程序集的绑定，到应用程序更新版本的程序集。 有关编辑绑定文件的详细信息，请参阅[自定义绑定文件](http://go.microsoft.com/fwlink/?LinkID=155000)(超链接"<http://go.microsoft.com/fwlink/?LinkID=155000>" <http://go.microsoft.com/fwlink/?LinkID=155000>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。