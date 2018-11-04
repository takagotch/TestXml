### TestXml
---
https://github.com/alovak/test_xml

```
gem install test_xml

```

```ruby
def test_item_representation
  assert_xml_equal "<item><id>1</id></item>", @item.to_xml
end

it "should contain the id" do
  @item.to_xml.should equal_xml(<<-XML)
    <item>
      <id>1</id>
    </item>
  XML
end

require 'test_xml/spec'
require 'test_xml/test_unit'
require 'test_xml/mini_test'



```

```
Scenario:
  When I post some data
  Then the response should match the following xml
  """
    <transaction>
      <status>success</status>
      <id/>
      <order_id/>
    </transaction>
  """
  
require 'test_xml'
require 'test_xml/spec'
World(TestXml::Spec)

Then /^the response should match the following xml$/ do |xml|
  response.body.should equal_xml(xml)
end

```
