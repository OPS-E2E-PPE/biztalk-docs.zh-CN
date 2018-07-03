---
title: 组件接口用户定义的方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- component interfaces, user-defined methods
- user-defined methods, component interface
- custom component interfaces, limitations
- collection limitations
- custom methods, samples
- samples, custom methods
- component interfaces, limitations for custom CI
ms.assetid: e4b15889-35ff-44aa-819d-eade9690bdd6
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68149876dc51d90b4dbc07772fd9b9b5c60fb7db
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022563"
---
# <a name="component-interface-user-defined-methods"></a>组件接口用户定义的方法
用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器在组件接口中支持用户定义的方法。 签名形式如下：  
  
```  
myRet=myCI.myMethod(parameter1, parameter2, ...)  
```  
  
 其中：  
  
- `parameter1` 和 `parameter2` 为输入参数。  
  
- `myRet` 为返回值。  
  
  这些参数只能是该方法的输入参数。 可能从该方法返回一个值作为返回参数。  
  
> [!NOTE]
>  包含用户定义方法的组件接口应该仅启用 PeopleSoft `Get` 函数。 如果组件接口具有密钥，则自定义方法将不起作用。  
  
## <a name="custom-ci-limitation"></a>自定义 CI 限制  
 用于 PeopleSoft Enterprise 的 BizTalk 适配器可以处理自定义 PeopleSoft 方法（假设组件接口不具有密钥）。 如果组件接口具有密钥，自定义方法将不起作用。  
  
### <a name="workaround"></a>解决方法  
 创建一个不具有密钥的新组件接口，并编写一个将密钥合并为调用参数一部分的新自定义方法。 例如，可以在 USER_PROFILE 组件接口中使用 SetPassword 自定义方法；但是，USER_PROFILE 具有密钥。 您可以创建一个不具有密钥的新组件接口，然后在新组件接口中创建一个自定义方法。 此方法将接受两个参数，用户 ID 和密码。 随后，自定义方法可以使用 `Get` 调用 USER_PROFILE，然后调用 `SetPassword`。 有关详细信息，请参考 PeopleSoft 文档。  
  
 由于 PeopleSoft 的限制，用户定义方法中显示的 `Date`、`DateTime` 和 `Time` 类型将映射为客户端代码中的字符串。  
  
## <a name="collection-limitation"></a>集合限制  
 用户定义的方法通常无法返回一个或多个集合以及任何 API 对象。 这意味着只能返回字符串和数字等简单类型。 您可以解除此限制，方法是将集合作为 XML 字符串发送并对客户端进行编程以解析字符串，从而将项目提取到正确的格式。 您可以检查 GET_CI_INFO 自定义组件接口，以查看此解决方法的示例。  
  
## <a name="sample-custom-method"></a>示例自定义方法  
 您可以使用以下基本自定义方法，SayHello，以便使用自定义方法来测试组件接口的功能。  
  
 以下 PeopleCode 函数是 PeopleSoft 组件接口的一个用户定义的方法，名为 ACB_EMPLOYEE。 该示例返回一个字符串，其中的返回值是**Hello**跟输入参数的值。  
  
```  
Function SayHello(&sName As string) Returns string  
      &EOL = Char(10);  
      &sResult = "Hello " | &sName | &EOL;  
      Return &sResult;  
End-Function;  
```  
  
> [!NOTE]
>  若要使用一个命令同时对多个表进行修改，可以创建另一个组件接口，或创建组件接口用户定义方法。  
  
## <a name="see-also"></a>请参阅  
 [附件 A：组件接口方法](../core/appendix-a-component-interface-methods.md)