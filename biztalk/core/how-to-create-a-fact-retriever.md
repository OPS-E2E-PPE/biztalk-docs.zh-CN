---
title: 如何创建事实检索器 |Microsoft Docs
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
ms.openlocfilehash: 1910d143aaac50d7690c4338c053873f70d2db38
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340050"
---
# <a name="how-to-create-a-fact-retriever"></a><span data-ttu-id="cccad-102">如何创建事实检索器</span><span class="sxs-lookup"><span data-stu-id="cccad-102">How to Create a Fact Retriever</span></span>
<span data-ttu-id="cccad-103">事实检索器是用于在其执行期间添加到策略的长期事实实例的组件。</span><span class="sxs-lookup"><span data-stu-id="cccad-103">A fact retriever is a component that is used to assert instances of long-term facts into a policy during its execution.</span></span> <span data-ttu-id="cccad-104">您可以实现**IFactRetriever**接口，并配置要在运行时使用此实现，以便在长期事实实例中的策略版本。</span><span class="sxs-lookup"><span data-stu-id="cccad-104">You can implement the **IFactRetriever** interface and configure a policy version to use this implementation at run time to bring in the long-term fact instances.</span></span> <span data-ttu-id="cccad-105">策略版本调用**UpdateFacts**上每个执行循环，如果事实检索器配置为该特定版本的事实检索器实现的方法。</span><span class="sxs-lookup"><span data-stu-id="cccad-105">The policy version invokes the **UpdateFacts** method of the fact retriever implementation on every execution cycle, if a fact retriever is configured for that particular version.</span></span>  
  
 <span data-ttu-id="cccad-106">您可以选择实现**IFactRemover**事实检索器组件上的接口。</span><span class="sxs-lookup"><span data-stu-id="cccad-106">You can optionally implement the **IFactRemover** interface on a fact retriever component.</span></span> <span data-ttu-id="cccad-107">规则引擎将调用**UpdateFactsAfterExecution**方法**IFactRemover**接口时将在释放策略。</span><span class="sxs-lookup"><span data-stu-id="cccad-107">The rule engine invokes the **UpdateFactsAfterExecution** method of the **IFactRemover** interface when the policy is disposed.</span></span> <span data-ttu-id="cccad-108">这可以执行任何执行后工作，例如提交任何数据库更改或取消任何对象实例的规则引擎工作内存中提供的机会。</span><span class="sxs-lookup"><span data-stu-id="cccad-108">This provides an opportunity to you to do any post-execution work such as committing any database changes or retracting any object instances from the rule engine's working memory.</span></span>  
  
## <a name="to-specify-a-fact-retriever-for-a-policy"></a><span data-ttu-id="cccad-109">若要指定策略的事实检索器</span><span class="sxs-lookup"><span data-stu-id="cccad-109">To specify a fact retriever for a policy</span></span>  
 <span data-ttu-id="cccad-110">您可以使用下面的代码配置规则集，使用名为"MyAssembly"作为事实检索器程序集中名为"检索器"的类。</span><span class="sxs-lookup"><span data-stu-id="cccad-110">You could use the following code to configure the rule set to use a class named "Retriever" in the assembly named "MyAssembly" as the fact retriever.</span></span>  
  
```  
RuleEngineComponentConfiguration fr = new RuleEngineComponentConfiguration("MyAssembly", "Retriever");  
RuleSet rs = new RuleSet("ruleset");  
// associate the execution configuration with a ruleset  
RuleSetExecutionConfiguration rsCfg = rs.ExecutionConfiguration;  
rsCfg.FactRetriever = factRetriever;  
```  
  
> [!NOTE]
>  <span data-ttu-id="cccad-111">如果作为 RuleEngineComponentConfiguration 构造函数的第一个参数指定简单程序集名称，如 MyAssembly，则 BizTalk 规则引擎将假定它是私有程序集并查找你的应用程序文件夹中的程序集。</span><span class="sxs-lookup"><span data-stu-id="cccad-111">If you specify simple assembly name such as MyAssembly as the first parameter for RuleEngineComponentConfiguration constructor, the BizTalk rule engine assumes that it is a private assembly and looks for the assembly in your application folder.</span></span> <span data-ttu-id="cccad-112">如果指定完全限定的程序集名称，例如**MyAssembly，版本 = 1.0.0.0，区域性 = 中性，PublicKeyToken = a310908b42c024fe**，规则引擎将假定它是共享的程序集并查找在全局程序集程序集缓存 (GAC)。</span><span class="sxs-lookup"><span data-stu-id="cccad-112">If you specify fully qualified assembly name such as **MyAssembly, Version=1.0.0.0, Culture=neutral, PublicKeyToken=a310908b42c024fe**, the rule engine assumes that it is a shared assembly and looks for the assembly in the global assembly cache (GAC).</span></span> <span data-ttu-id="cccad-113">您可以找到在简单和完全限定的程序集名称的定义[ http://go.microsoft.com/fwlink/?LinkId=64535 ](http://go.microsoft.com/fwlink/?LinkId=64535)。</span><span class="sxs-lookup"><span data-stu-id="cccad-113">You can find the definitions of simple and fully qualified assembly names at [http://go.microsoft.com/fwlink/?LinkId=64535](http://go.microsoft.com/fwlink/?LinkId=64535).</span></span>  
  
 <span data-ttu-id="cccad-114">您可以设计具有所需的特定于应用程序逻辑，以连接到所需的数据源，断言将数据作为长期事实添加到引擎，并指定刷新或添加到的长期事实数据的新实例的逻辑事实检索器引擎。</span><span class="sxs-lookup"><span data-stu-id="cccad-114">You can design the fact retriever with the required application-specific logic to connect to the required data sources, assert the data as long-term facts into the engine, and specify the logic for refreshing or asserting new instances of the long-term facts into the engine.</span></span> <span data-ttu-id="cccad-115">直到更新，将在后续的执行循环上使用是最初添加到引擎中并随后缓存的值。</span><span class="sxs-lookup"><span data-stu-id="cccad-115">Until updated, the values that are initially asserted into the engine and consequently cached will be used on subsequent execution cycles.</span></span> <span data-ttu-id="cccad-116">事实检索器实现将返回一个对象，它类似于标记，并可以在连同**factsHandleIn**对象，以确定是否要更新现有事实或添加新的事实。</span><span class="sxs-lookup"><span data-stu-id="cccad-116">The fact retriever implementation returns an object that is analogous to a token and can be used along with the **factsHandleIn** object to determine whether to update existing facts or assert new facts.</span></span> <span data-ttu-id="cccad-117">当策略版本首次调用其事实检索器时**factsHandleIn**对象始终为 null，然后在事实检索器执行之后会返回对象的值。</span><span class="sxs-lookup"><span data-stu-id="cccad-117">When a policy version calls its fact retriever for the first time, the **factsHandleIn** object is always null and then takes the value of the return object after the fact retriever's execution.</span></span>  
  
 <span data-ttu-id="cccad-118">请注意，对于相同的规则引擎实例，长期事实只需添加一次。</span><span class="sxs-lookup"><span data-stu-id="cccad-118">Note that for the same rule engine instance, a long-term fact only needs to be asserted once.</span></span> <span data-ttu-id="cccad-119">例如，使用**调用规则**形状在业务流程，该策略实例移动到内部缓存。</span><span class="sxs-lookup"><span data-stu-id="cccad-119">For example, when you use the **Call Rules** shape in an orchestration, the policy instance is moved into an internal cache.</span></span> <span data-ttu-id="cccad-120">在此期间，取消所有短期事实，并保留长期事实。</span><span class="sxs-lookup"><span data-stu-id="cccad-120">At this time, all short-term facts are retracted and long-term facts are kept.</span></span> <span data-ttu-id="cccad-121">如果调用同一策略同样，相同的业务流程实例或同一主机中的不同业务流程实例此策略实例是从缓存中提取和重复使用。</span><span class="sxs-lookup"><span data-stu-id="cccad-121">If the same policy is called again, either by the same orchestration instance or by a different orchestration instance in the same host, this policy instance is fetched from the cache and reused.</span></span> <span data-ttu-id="cccad-122">在某些批处理环境，可以创建同一策略的多个策略实例。</span><span class="sxs-lookup"><span data-stu-id="cccad-122">In some batch processing scenarios, several policy instances of the same policy could be created.</span></span> <span data-ttu-id="cccad-123">如果创建新的策略实例，则必须确保添加正确的长期事实。</span><span class="sxs-lookup"><span data-stu-id="cccad-123">If a new policy instance is created, you must ensure that the correct long-term facts are asserted.</span></span>  
  
 <span data-ttu-id="cccad-124">此外，你将需要编写自定义代码以实现以下策略：</span><span class="sxs-lookup"><span data-stu-id="cccad-124">Additionally, you would need to write custom code to implement the following strategies:</span></span>  
  
- <span data-ttu-id="cccad-125">了解何时更新长期事实</span><span class="sxs-lookup"><span data-stu-id="cccad-125">Know when to update the long-term facts</span></span>  
  
- <span data-ttu-id="cccad-126">跟踪的规则引擎所使用的长期事实</span><span class="sxs-lookup"><span data-stu-id="cccad-126">Keep track of which rule engine instance uses which long-term facts</span></span>  
  
  <span data-ttu-id="cccad-127">下面的示例代码显示了不同的事实检索器实现，与 MyPolicy 将 mytableinstance 添加为长期事实，使用不同的绑定类型相关联。</span><span class="sxs-lookup"><span data-stu-id="cccad-127">The following sample code shows different fact retriever implementations, which are associated with MyPolicy to assert MyTableInstance as a long-term fact, using different binding types.</span></span>  
  
## <a name="datatable-binding"></a><span data-ttu-id="cccad-128">DataTable 绑定</span><span class="sxs-lookup"><span data-stu-id="cccad-128">DataTable binding</span></span>  
  
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
  
## <a name="datarow-binding"></a><span data-ttu-id="cccad-129">DataRow 绑定</span><span class="sxs-lookup"><span data-stu-id="cccad-129">DataRow binding</span></span>  
  
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
  
 <span data-ttu-id="cccad-130">下面的示例代码演示如何添加事实检索器实现中的.NET 和 XML 事实。</span><span class="sxs-lookup"><span data-stu-id="cccad-130">The following sample code demonstrates how to assert .NET and XML facts in a fact retriever implementation.</span></span>  
  
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
  
## <a name="dataconnection-binding"></a><span data-ttu-id="cccad-131">DataConnection 绑定</span><span class="sxs-lookup"><span data-stu-id="cccad-131">DataConnection Binding</span></span>  
  
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
  
 <span data-ttu-id="cccad-132">请注意， **DataConnection**s 应始终重新添加，提供从事实检索器，如上面的代码示例中所示。</span><span class="sxs-lookup"><span data-stu-id="cccad-132">Note that **DataConnection**s should always be reasserted, when provided from a fact retriever, as shown in the preceding code sample.</span></span> <span data-ttu-id="cccad-133">引擎实例使用**DataConnection**根据规则条件，查询数据库并由查询返回任何行将其添加到引擎的工作内存中作为**TypedDataRow**s。</span><span class="sxs-lookup"><span data-stu-id="cccad-133">The engine instance uses the **DataConnection** to query the database based on the rule conditions, and any rows returned by the query would be asserted into the engine's working memory as **TypedDataRow**s.</span></span> <span data-ttu-id="cccad-134">Reasserting DataConnection 可以确保在引擎上一次执行中的行，会从内存清除。</span><span class="sxs-lookup"><span data-stu-id="cccad-134">Reasserting the DataConnection ensures that rows from a previous execution of the engine are cleared from memory.</span></span>  
  
 <span data-ttu-id="cccad-135">实际上，没有什么优势断言**DataConnection**通过事实检索器，不同之处提供了一种方法来具体化数据源。</span><span class="sxs-lookup"><span data-stu-id="cccad-135">In fact, there is little advantage to asserting a **DataConnection** through a fact retriever except that it provides a way to externalize the data source.</span></span>