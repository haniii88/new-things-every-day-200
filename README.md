```javascript
function dailyLog200() {
  const expenses = [
    { category: "Food", amount: 25 },
    { category: "Transport", amount: 12 },
    { category: "Food", amount: 18 },
    { category: "Entertainment", amount: 30 },
    { category: "Shopping", amount: 45 },
  ];

  const summary = expenses.reduce((result, expense) => {
    result[expense.category] =
      (result[expense.category] || 0) + expense.amount;

    return result;
  }, {});

  const total = expenses.reduce(
    (sum, expense) => sum + expense.amount,
    0
  );

  console.log("=== Daily Expense Report ===");
  console.log(`Total Spent: $${total}`);

  Object.entries(summary).forEach(([category, amount]) => {
    console.log(`${category}: $${amount}`);
  });

  console.log(
    `Average Expense: $${(total / expenses.length).toFixed(2)}`
  );
}

dailyLog200();
```
