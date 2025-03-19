Typed EventTarget - idea from https://dev.to/marcogrcr/type-safe-eventtarget-subclasses-in-typescript-1nkf

```
import { type TypedEventTarget } from './typedet'

export type TypedEvent = {
    name: string
}

export class EventClass extends (EventTarget as TypedEventTarget<{
    onapplied: CustomEvent<Filter[]>
}>){

    public apply(): void {
        this.dispatchEvent(new CustomEvent<Filter[]>('onapplied', {detail: this.name}))
    }
}```