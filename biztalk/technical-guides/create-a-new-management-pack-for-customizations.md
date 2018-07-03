---
title: 为自定义项创建新的管理包 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4ce1ffa0-57c7-41ce-b459-48c36522889e
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3108696e89e6a411049c11929c8e7dcb7f48db34
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016794"
---
# <a name="create-a-new-management-pack-for-customizations"></a>为自定义项创建新的管理包
大多数供应商管理包被密封的不能更改任何管理包文件中的原始设置。 但是，您可以创建自定义，例如替代或新的监视对象，然后将它们保存到不同管理包。 默认情况下，Operations Manager 2007 R2/2012年将所有自定义项保存到默认管理包。 作为最佳做法，应改为创建单独的管理包为你想要自定义每个密封的管理包。  
  
 创建新管理包来存储替代具有下列优势：  
  
- 简化了将测试和预生产环境中创建的自定义导出到生产环境的过程。 例如，而无需导出包含来自多个管理包自定义项的默认管理包，可以导出只包含单个管理包的自定义管理包。  
  
- 而不必首先删除默认管理包，可以删除原始管理包。 包含自定义项的管理包依赖于原始管理包。 这种依赖性要求删除包含自定义的管理包后，才能删除原始管理包。 如果所有自定义保存到默认管理包，必须删除默认管理包，然后才能删除原始管理包。  
  
- 跟踪和更新单个管理包的自定义变得更加简单。  
  
  有关详细信息大约密封和未密封管理包，请参阅[管理包格式](http://go.microsoft.com/fwlink/?LinkID=198193)(http://go.microsoft.com/fwlink/?LinkId=198193)。 有关管理包自定义的详细信息，请参阅[自定义管理包](http://go.microsoft.com/fwlink/?LinkID=198194)(http://go.microsoft.com/fwlink/?LinkID=198194)。