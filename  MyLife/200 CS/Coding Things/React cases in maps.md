



```typescript

export default function EventDashboard() {

const [editStates, setEditStates] = useState<Record<string, boolean>>({});

const [editValues, setEditValues] = useState<

Record<string, Partial<EventData>>

>({});

  

const toggleEdit = (uid: string, event?: EventData) => {

setEditStates((prev) => ({ ...prev, [uid]: !prev[uid] }));

  

if (event) {

setEditValues((prev) => ({

...prev,

[uid]: {

//Data

},

}));

}

};

  

useEffect(() => {

const fetchData = async () => {

const events: EventData[] = (await getAllEvents()) as EventData[];

setEventsData(events);

};

  

fetchData();

}, []);

  

const saveUserChanges = async (uid: string) => {

const updated = editValues[uid];

if (!updated) return;


await updateUser(uid, updated); 
  

setEditStates((prev) => ({ ...prev, [uid]: false }));

};

  

```

