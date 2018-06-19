---
title: XPath |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 444b5eb9-0c00-4225-918e-b973532c67d0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ee46838596a55512df5d1476f2c3ba34b1f5cb9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289645"
---
# <a name="xpath"></a>XPath
推送 XPath 语句所指示的值。  
  
## <a name="syntax"></a>语法  
  
```  
  
<wcf:Operation Name="XPath">  
  <wcf:Argument>//po:POID</wcf:Argument>  
</wcf:Operation>  
```  
  
#### <a name="parameters"></a>Parameters  
 有效 XPath 语句。  
  
## <a name="pushed-value"></a>推送的值  
 执行 XPath 语句所找到的结果的字符串值。  
  
## <a name="remarks"></a>注释  
 必须使用有效的 XPath 语句。  
  
 在出现多个匹配的情况下，仅会使用第一个匹配。  
  
## <a name="example"></a>示例  
 下面的示例表达式通过将常数“C_”与当前消息中的采购订单 ID 相连接构造了一个相关值。 采购订单 ID 通过 XPath 运算检索。  
  
```  
<ic:CorrelationID>  
  <ic:Expression>  
    <ic:Operation Name="Constant">  
      <ic:Argument>C_</ic:Argument>  
    </ic:Operation>  
    <wcf:Operation Name="XPath">  
      <wcf:Argument>//po:POID</wcf:Argument>  
    </wcf:Operation>  
    <ic:Operation Name="Concatenate" />  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
## <a name="see-also"></a>另请参阅  
 [Windows Communication Foundation 中的操作](../core/operations-in-windows-communication-foundation.md)