# Conditional rendering

use the if JS operator to decide which component to render (`<MadeGoal/>` or `<MissedGoal/>`)
```bash
function Goal(props) {
  const isGoal = props.isGoal;
  if (isGoal) {
    return <MadeGoal/>;
  }
  return <MissedGoal/>;
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Goal isGoal={false} />);
```