---
title: 如何选择多个 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51f4528c-4846-4e02-9591-07e2fde131ae
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4cb72a036acaa39823c7cd2e4c3ab18ba4330dcc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334775"
---
# <a name="how-to-select-multiple-functoids"></a>如何选择多个 Functoid
当处理大型映射，您可能想要在同一时间执行对多个 functoid 的操作。 在这种情况下，可以选择所有目标 functoid，然后执行操作。 这很有用，例如，如果想要连接的 functoid 及其连接的链接，以及一组移到另一个网格页。  
  
### <a name="to-select-multiple-functoids-at-the-same-time"></a>若要同时选择多个 functoid  
  
1.  在 BizTalk 映射器网格页上，单击第一个 functoid 以将其选中。 该 functoid 将突出显示。  
  
2.  在 BizTalk 映射器中，在相同的网格页中，按住 CTRL 或 SHIFT 键，然后单击另一个 functoid 将其同时选定。 此 functoid 也会突出显示。  
  
3.  重复步骤 2 所需选择所有目标 functoid。  
  
    > [!NOTE]
    >  在网格页中的多项选择为 functoid 和链接同时工作，移动一系列连接的 functoid 和其连接到另一个链接从一个网格页时必须签名。  
  
## <a name="see-also"></a>请参阅  
 [使用 Functoid 创建更复杂的映射](../core/using-functoids-to-create-more-complex-mappings.md)   
 [如何选择多个链接和 Functoid](../core/how-to-select-multiple-links-and-functoids.md)