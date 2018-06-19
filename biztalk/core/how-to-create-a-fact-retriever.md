---
title: 如何创建事实检索器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IFactRetriever interface
- Business Rules Framework, bindings
- factsHandleIn object
- Business Rules Framework, code samples
- Business Rules Framework, fact retrievers
- UpdateFacts method
- Business Rules Framework, programming
ms.assetid: 503dc769-3ada-4099-a5fe-4dd03d995600
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20ea60356580ae7d5a6ac2be3336ec07314211f1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22250205"
---
# <a name="how-to-create-a-fact-retriever"></a>如何创建事实检索器
事实检索器是在策略执行期间用来将长期事实实例添加到该策略中的组件。 你可以实现**IFactRetriever**接口，并配置为策略版本，以在运行时使用此实现，以使保持长期的事实实例。 策略版本时，将调用**UpdateFacts**上每个执行周期，如果事实检索器配置为该特定版本的事实检索器实现的方法。  
  
 你可以选择实现**IFactRemover**事实检索器组件上的接口。 规则引擎时，将调用**UpdateFactsAfterExecution**方法**IFactRemover**接口时释放策略。 这使您可以有机会进行执行后工作，例如提交任何数据库更改或从规则引擎的工作内存取消任何对象实例。  
  
## <a name="to-specify-a-fact-retriever-for-a-policy"></a>为策略指定事实检索器  
 您可以使用以下代码配置规则集，使用“MyAssembly”程序集中的“Retriever”类作为事实检索器。  
  
```  
RuleEngineComponentConfiguration fr = new RuleEngineComponentConfiguration("MyAssembly", "Retriever");  
RuleSet rs = new RuleSet("ruleset");  
// associate the execution configuration with a ruleset  
RuleSetExecutionConfiguration rsCfg = rs.ExecutionConfiguration;  
rsCfg.FactRetriever = factRetriever;  
```  
  
> [!NOTE]
>  如果指定简单程序集名称（如 MyAssembly）作为 RuleEngineComponentConfiguration 构造函数的第一个参数，则 BizTalk 规则引擎将假定它是私有程序集，并在应用程序文件夹中查找该程序集。 如果指定完全限定程序集名称，如**MyAssembly，Version = 1.0.0.0，Culture = neutral，PublicKeyToken = a310908b42c024fe**，规则引擎假定它是共享的程序集，查找在全局程序集程序集缓存 (GAC)。 你可以找到在简单和完全限定的程序集名称的定义[http://go.microsoft.com/fwlink/?LinkId=64535](http://go.microsoft.com/fwlink/?LinkId=64535)。  
  
 您可以使用所需的特定于应用程序的逻辑来设计事实检索器以连接所需的数据源，将该数据作为长期事实添加到到引擎中，并指定刷新或向引擎中添加新的长期事实实例的逻辑。 只有在更新之后，最初添加到引擎中并随后缓存的值才将用于后续的执行循环。 事实检索器实现返回一个对象，它类似于一个令牌，并可用于沿**factsHandleIn**对象来确定是否要更新现有的事实数据或断言新事实。 当策略版本首次调用其事实检索器**factsHandleIn**对象始终为 null，然后将在之后的事实检索执行返回的对象的值。  
  
 请注意，对于同一规则引擎实例，一个长期事实只需添加一次。 例如，当使用**调用规则**形状中业务流程、 策略实例移动到内部缓存。 此时，将取消所有短期事实，并保留所有长期事实。 如果同一策略由同一业务流程实例或同一主机中的不同业务流程实例再次调用，则将从缓存中提取此策略实例并重新使用。 在某些批处理环境中，可以创建同一策略的多个策略实例。 如果创建新的策略实例，则必须确保添加了正确的长期事实。  
  
 此外，您需要编写自定义代码以实现以下策略：  
  
-   了解何时更新长期事实  
  
-   跟踪规则引擎所使用的长期事实  
  
 下面的示例代码显示了不同的事实检索器实现，它们使用不同的绑定类型与 MyPolicy 相关联以将 MyTableInstance 添加为长期事实。  
  
## <a name="datatable-binding"></a>DataTable 绑定  
  
```  
using System;  
using System.Xml;  
using System.Collections;  
using Microsoft.RuleEngine;  
using System.IO;  
using System.Data;  
using System.Data.SqlClient;  
namespace MyBizTalkApplication.FactRetriever  
{  
   public class myFactRetriever:IFactRetriever  
   {  
      public object UpdateFacts(RuleSetInfo rulesetInfo, Microsoft.RuleEngine.RuleEngine engine, object factsHandleIn)  
      {  
         object factsHandleOut;  
         if (factsHandleIn == null)   
  
         {  
            SqlDataAdapter dAdapt = new SqlDataAdapter();  
            dAdapt.TableMappings.Add("Table", "CustInfo");  
            SqlConnection conn = new SqlConnection("Initial Catalog=Northwind;Data Source=(local);Integrated Security=SSPI;");  
            conn.Open();  
            SqlCommand myCommand = new SqlCommand("SELECT * FROM CustInfo", conn);  
            myCommand.CommandType = CommandType.Text;  
            dAdapt.SelectCommand = myCommand;  
            DataSet ds = new DataSet("Northwind");  
            dAdapt.Fill(ds);  
            TypedDataTable tdt = new TypedDataTable(ds.Tables["CustInfo"]);  
            engine.Assert(tdt);  
            factsHandleOut = tdt;  
         }  
  
         else  
            factsHandleOut = factsHandleIn;  
         return factsHandleOut;  
      }  
   }  
}  
```  
  
## <a name="datarow-binding"></a>DataRow 绑定  
  
```  
using System;  
using System.Xml;  
using System.Collections;  
using Microsoft.RuleEngine;  
using System.IO;  
using System.Data;  
using System.Data.SqlClient;  
namespace MyBizTalkApplication.FactRetriever  
{  
   public class myFactRetriever:IFactRetriever  
   {  
  
      public object UpdateFacts(RuleSetInfo rulesetInfo, Microsoft.RuleEngine.RuleEngine engine, object factsHandleIn)  
      {  
         object factsHandleOut;  
         if (factsHandleIn == null)   
  
         {  
            SqlDataAdapter dAdapt = new SqlDataAdapter();  
            dAdapt.TableMappings.Add("Table", "CustInfo");  
            SqlConnection conn = new SqlConnection("Initial Catalog=Northwind;Data Source=(local);Integrated Security=SSPI;");  
            conn.Open();  
            SqlCommand myCommand = new SqlCommand("SELECT * FROM CustInfo", conn);  
            myCommand.CommandType = CommandType.Text;  
            dAdapt.SelectCommand = myCommand;  
            DataSet ds = new DataSet("Northwind");  
            dAdapt.Fill(ds);  
            TypedDataTable tdt = new TypedDataTable(ds.Tables["CustInfo"]);  
  
            // binding to the first row of CustInfo table  
            TypedDataRow tdr = new TypedDataRow(ds.Tables["CustInfo"].Rows[0],tdt);  
            engine.Assert(tdr);  
            factsHandleOut = tdr;     
         }  
         else  
            factsHandleOut = factsHandleIn;  
         return factsHandleOut;  
      }  
   }   
}  
```  
  
 下面的示例代码演示了如何在事实检索器实现中添加 .NET 和 XML 事实。  
  
```  
using System;  
using System.Xml;  
using System.Collections;  
using Microsoft.RuleEngine;  
using System.IO;  
using System.Data;  
using System.Data.SqlClient;  
namespace MyBizTalkApplication.FactRetriever  
{  
   public class myFactRetriever:IFactRetriever  
   {  
      public object UpdateFacts(RuleSetInfo rulesetInfo, Microsoft.RuleEngine.RuleEngine engine, object factsHandleIn)  
      {  
         object factsHandleOut;  
         if (factsHandleIn == null)   
         {  
            //create .NET object instances  
            bookInstance = new Book();  
            magazineInstance = new Magazine();              
  
            //create an instance of the XML object  
            XmlDocument xd = new XmlDocument();  
  
            //load the document  
            xd.Load(@"..\myXMLInstance.xml");  
  
            //create and instantiate an instance of TXD  
            TypedXmlDocument doc = new TypedXmlDocument("mySchema",xd1);  
  
            engine.Assert(bookInstance);  
            engine.Assert(magazineInstance);  
            engine.Assert(doc);  
            factsHandleOut = doc;  
         }  
         else  
            factsHandleOut = factsHandleIn;  
         return factsHandleOut;  
      }  
   }  
}  
```  
  
## <a name="dataconnection-binding"></a>DataConnection 绑定  
  
```  
using System;  
using System.Xml;  
using System.Collections;  
using Microsoft.RuleEngine;  
using System.IO;  
using System.Data;  
using System.Data.SqlClient;  
namespace MyBizTalkApplication.FactRetriever  
{  
   public class myFactRetriever:IFactRetriever  
   {  
      public object UpdateFacts(RuleSetInfo rulesetInfo, Microsoft.RuleEngine.RuleEngine engine, object factsHandleIn)  
      {  
         object factsHandleOut;  
  
         {   
            string strCmd = "Initial Catalog=Northwind;Data Source=(local);Integrated Security=SSPI;";  
            SqlConnection conn = new SqlConnection(strCmd);  
            DataConnection dc = new DataConnection("Northwind", "CustInfo", conn);  
  
            engine.Assert(dc);  
            factsHandleOut = dc;           
         }  
         return factsHandleOut;  
      }  
   }  
}  
```  
  
 请注意，**该组**s 应始终 reasserted 时提供从事实检索器，如上面的代码示例中所示。 引擎实例使用**该组**基于规则条件中，在数据库中查询和查询返回的任何行将断言到引擎的工作内存**TypedDataRow**s。 Reasserting 数据连接可确保从引擎上一次执行的行从内存中清除。  
  
 实际上，没有什么好处到断言**该组**通过一个事实，不同之处检索器使您能够外部化的数据源。