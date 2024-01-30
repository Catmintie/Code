## 创建一个输入框
<input type="text">
注意 input 输入框是没有结束标签的。

## 给输入框添加占位符文本（默认填入）
<input type="text" placeholder="this is placeholder text">

## 创建一个表单
<form action="url-where-you-want-to-submit-form-data">
<input>
</form>

## 给表单添加提交按钮
<button type="submit">this button submits the form</button>

## 给表单添加一个必填字段
如果你想把文本输入框设置为必填项，在 input 元素中加上 required 属性就可以了，例如：<input type="text" required>

## 创建一组单选按钮（radio buttons）
<label>
<input type="radio" name="indoor-outdoor">Indoor
</label>
所有关联的单选按钮应该拥有相同的 name 属性。 创建一组单选按钮，选中其中一个按钮，其他按钮即显示为未选中，以确保用户只提供一个答案。
最佳实践是在 label 元素上设置 for 属性，让其值与相关联的 input 单选按钮的 id 属性值相同。 这使得辅助技术能够在标签和相关的 input 元素之间建立关联关系。 例如：
<label for="indoor">
<input id="indoor" type="radio" name="indoor-outdoor">Indoor
</label>

## 创建一组复选框（checkboxes）
<label for="loving"><input id="loving" type="checkbox" name="personality"> Loving</label>
每一个复选框都应该嵌套在它自己的 label（标签）元素中。 这样，我们相当于给 input 元素和包裹它的 label 元素建立起了对应关系。
所有关联的复选框应该拥有相同的 name 属性。
使得 input 与 label 关联的最佳实践是在 label 元素上设置 for 属性，让其值与相关联的 input 复选框的 id 属性值相同。

## 给单选按钮和复选框添加默认选中项
只需将单词 checked 添加到 input 元素的内部：<input type="radio" name="test-name" checked>


